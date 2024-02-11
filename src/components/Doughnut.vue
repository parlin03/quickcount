<template>
 <b-container class="bv-example-row mt-3">
    <b-row>
      
      <b-col cols="12" md="8">
        <b-row >
          <b-col>
            <div >
            <b-card
                style="max-width: 20rem; text-align: center;"
                class="mb-2"
              >   
                <b-card-title style="font-size: 12px;">Total DPT</b-card-title>

                <b-card-text >
                  <h5>{{total_dpt}}</h5>
                </b-card-text>

              </b-card>
            </div>
          </b-col>
          <b-col>
              <b-card
                style="max-width: 20rem; text-align: center; "
                class="mb-2"
              >
                <b-card-title style="font-size: 12px;">Suara Masuk</b-card-title>
                <b-card-text>
                  <h5>{{total_suara}}</h5>
                </b-card-text>

              </b-card>
           </b-col>
           <b-col>
              <b-card
                style="max-width: 20rem; text-align: center;"
                class="mb-1"
              >
                <b-card-title style="font-size: 12px;">Total TPS</b-card-title>
                <b-card-text>
                  <!-- <h5>{{total_rusak}}</h5> -->
                  <h5>{{total_tps}} </h5>
                </b-card-text>

              </b-card>
           </b-col>
           <b-col>
              <b-card
                style="max-width: 20rem; text-align: center;"
                class="mb-1"
              >
                <b-card-title style="font-size: 12px;">TPS Masuk</b-card-title>
                <b-card-text>
                  <!-- <h5>{{total_rusak}}</h5> -->
                  <h5>{{tps_masuk}} <span  style="color:blue;font-size: 0.9rem">({{ total_percent }}%)</span></h5>
                </b-card-text>

              </b-card>
           </b-col>
        </b-row>
        <b-row>
          <TableComponent/>
        </b-row>
      </b-col>

      <b-col cols="6" md="4" style="font-size: 0.5rem;">
         <Doughnut
            :chart-options="chartOptions"
            :chart-data="chartData"
            :chart-id="chartId"
            :dataset-id-key="datasetIdKey"
            :plugins="plugins"
            :css-classes="cssClasses"
            :styles="styles"
            :width="width"
            :height="height"
            :scales="scales"
          />
      </b-col>
    </b-row>

  </b-container>
 
</template>

<script>
import TableComponent from '../components/Tables.vue';  
import { Doughnut } from 'vue-chartjs/legacy'

import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  ArcElement,
  CategoryScale
} from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, ArcElement, CategoryScale)
ChartJS.defaults.font.size = 6

export default {
  name: 'DoughnutChart',
  components: {
    Doughnut,
    TableComponent
  },
  props: {
    chartId: {
      type: String,
      default: 'doughnut-chart'
    },
    datasetIdKey: {
      type: String,
      default: 'label'
    },
    width: {
      type: Number,
      default: 200
    },
    height: {
      type: Number,
      default: 220
    },
    cssClasses: {
      default: '',
      type: String
    },
    styles: {
      type: Object,
      default: () => {}
    },
    plugins: {
      type: Array,
      default: () => []
    },
    scales: {
           x: {
               display: true,
               size: 30
           }
    }
  },
  data() {
    return {
      total_dpt:"",
      total_tps:"",
      total_suara:"",
      tps_masuk:"",
      total_percent:"",
      chartData:[],
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false
      }
    }
  },
  methods: {
   
    loadTotalAll() {
      const baseURI = this.$settings.endPoint + "data/totalall";

      return this.$http.get(baseURI).then((response) => {
        const hasil = response.data.hasil;
        this.total_dpt=hasil.total_dpt;
        this.total_suara=hasil.total_suara;
        this.total_tps=hasil.total_tps;
        this.tps_masuk=hasil.tps_masuk;
        const pc=((hasil.tps_masuk/hasil.total_tps)*100)
        this.total_percent =pc.toFixed(1)
      });
    },


    loadCalon() {
      const baseURI = this.$settings.endPoint + "data/calon";

      return this.$http.get(baseURI).then((response) => {
        const hasil = response.data.hasil;
        let dataAWal={
          labels: [],
          datasets: [
            {
              backgroundColor: ['#B8860B','#42afee', '#9932CC', '#F0E68C', '#006400', '#FF69B4', '#000080'],
              data: []
            }
          ]
        }

        let percent=0;
        hasil.forEach((value) => {
            percent=(value.jml_suara/this.total_dpt)*100;           
            dataAWal.labels.push(value.nama_calon);
            dataAWal.datasets[0].data.push(percent);

        });
        this.chartData=dataAWal;
      });
    },


  },
  created() {
    setInterval(this.loadTotalAll, 1000);
    setInterval(this.loadCalon, 1000);
  },
  mounted() {
    this.loadTotalAll();
    this.loadCalon();
    
    
    // axios
    //   .get("https://www.themealdb.com/api/json/v1/1/categories.php")
    //   .then(response => {
    //     this.meals = response.data.categories;
    //   })
    //   .catch(err => {
    //     console.log(err);
    //   });
  },
}
</script>
