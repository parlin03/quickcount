<template>
  <b-container class="bv-example-row bv-example-row-flex-cols mt-3">
    <b-row class="fluid">
      <b-col>
        <b-card
          img-src="calon0.jpg"
          img-alt="Image"
          img-top

          style="width: 6rem; height: 13rem; text-align: center"
          class="mb-0"
        >
        <b-card-text>
          <b-row>
              <b-col style="background-color: #B8860B; color: white; font-size: 1rem; font-weight: bold;">{{jml_suara0}}</b-col>
          </b-row>
          <!-- <b-row>
              <b-col style="background-color: #B8860B; color: white">
              {{persen0}} %
            </b-col>
          </b-row> -->
          <b-row class="mt-3">
              <b-col style="font-size: 0.4rem; font-weight: bolder;">{{nama_calon0}}</b-col>
          </b-row>
        </b-card-text>
        </b-card>
      </b-col>


      <b-col>
        <b-card
          
          img-src="calon1.jpg"
          img-alt="Image"
          img-top
  
          style="width: 6rem; height: 13rem; text-align: center"
          class="mb-0"
        >
          <b-card-text>
            <b-row>
              <b-col style="background-color: #42afee; color: white; font-size: 1rem; font-weight: bold;">{{jml_suara1}}</b-col>
            </b-row>
            <!-- <b-row>
              <b-col style="background-color: #42afee; color: white">{{persen1}} %
              </b-col>
            </b-row> -->
            <b-row class="mt-1">
              <b-col style="font-size: 0.4rem; font-weight: bolder;">{{nama_calon1}}</b-col>
            </b-row>
          </b-card-text>
        </b-card>
      </b-col>


      <b-col>
        <b-card
          
          img-src="calon2.jpeg"
          img-alt="Image"
          img-top
  
          style="width: 6rem; height: 13rem; text-align: center"
          class="mb-0"
        >
        <b-card-text>
            <b-row>
              <b-col style="background-color: #9932CC; color: white;font-size: 1rem; font-weight: bold;">{{jml_suara2}}</b-col>
            </b-row>
            <!-- <b-row>
              <b-col style="background-color: #9932CC; color: white">
                {{persen2}} %
              </b-col>
            </b-row> -->
            <b-row class="mt-2">
              <b-col style="font-size: 0.4rem; font-weight: bolder;">{{nama_calon2}}</b-col>
            </b-row>
          </b-card-text>
        </b-card>
      </b-col>


      <b-col>
        <b-card
          img-src="calon3.jpeg"
          img-alt="Image"
          img-top
  
          style="width: 6rem; height: 13rem; text-align: center"
          class="mb-0"
        >
        <b-card-text>
          <b-row>
              <b-col style="background-color: #F0E68C; color: white;font-size: 1rem; font-weight: bold;">{{jml_suara3}}</b-col>
          </b-row>
          <!-- <b-row>
              <b-col style="background-color: #F0E68C; color: white">
              {{persen3}} %
            </b-col>
          </b-row> -->
          <b-row class="mt-2">
              <b-col style="font-size: 0.4rem; font-weight: bolder;">{{nama_calon3}}</b-col>
          </b-row>
        </b-card-text>
        </b-card>
      </b-col>


      <b-col>
        <b-card
          img-src="calon4.jpeg"
          img-alt="Image"
          img-top
  
          style="width: 6rem; height: 13rem; text-align: center"
          class="mb-0"
        >
        <b-card-text>
          <b-row>
              <b-col style="background-color: #006400; color: white;font-size: 1rem; font-weight: bold;">{{jml_suara4}}</b-col>
          </b-row>
          <!-- <b-row>
              <b-col style="background-color: #006400; color: white">
              {{persen4}} %
            </b-col>
          </b-row> -->
          <b-row class="mt-3">
              <b-col style="font-size: 0.4rem; font-weight: bolder;">{{nama_calon4}}</b-col>
          </b-row>
        </b-card-text>
        </b-card>
      </b-col>


      <b-col>
        <b-card
          img-src="calon5.jpeg"
          img-alt="Image"
          img-top
  
          style="width: 6rem; height: 13rem; text-align: center"
          class="mb-0"
        >
        <b-card-text>
          <b-row>
              <b-col style="background-color: #FF69B4; color: white; font-size: 1rem; font-weight: bold;">{{jml_suara5}}</b-col>
          </b-row>
          <!-- <b-row>
              <b-col style="background-color: #FF69B4; color: white">
              {{persen5}} %
            </b-col>
          </b-row> -->
          <b-row class="mt-2">
              <b-col style="font-size: 0.4rem; font-weight: bolder;">{{nama_calon5}}</b-col>
          </b-row>
        </b-card-text>
        </b-card>
      </b-col>


      <b-col>
        <b-card
          img-src="calon6.jpeg"
          img-alt="Image"
          img-top
  
          style="width: 6rem; height: 13rem; text-align: center"
          class="mb-0"
        >
        <b-card-text>
          <b-row>
            <b-col  style="background-color: #000080; color: white;font-size: 1rem; font-weight: bold;">{{jml_suara6}}</b-col>
          </b-row>
          <!-- <b-row>
              <b-col style="background-color: #000080; color: white">
              {{persen6}} %
            </b-col>
          </b-row> -->
          <b-row class="mt-2">
            <b-col style="font-size: 0.4rem; font-weight: bolder;">{{nama_calon6}}</b-col>
          </b-row>
        </b-card-text>
        </b-card>
      </b-col>
      
    </b-row>
  </b-container>
</template>

<script>
// import axios from "axios";
export default {
  data() {
    return {
      publicPath: process.env.BASE_URL,
      featchCalon: [],
      total_dtp:"",
      total_rusak:"",
      total_suara:"",
      jml_suara0:"",
      jml_suara1:"",
      jml_suara2:"",
      jml_suara3:"",
      jml_suara4:"",
      jml_suara5:"",
      jml_suara6:"",
      persen0:"",
      persen1:"",
      persen2: "",
      persen3: "",
      persen4: "",
      persen5: "",
      persen6: "",
      nama_calon0:"",
      nama_calon1:"",
      nama_calon2:"",
      nama_calon3:"",
      nama_calon4:"",
      nama_calon5:"",
      nama_calon6:"",
    };
  },
  methods: {
    loadCalonSatuan() {
      //this.featchCalon=[];
      const baseURI = this.$settings.endPoint + "data/calonsatuan";

      return this.$http.get(baseURI).then((response) => {
        const hasil = response.data.hasil;  
        this.jml_suara0=hasil.jml_suara0;
        this.jml_suara1=hasil.jml_suara1;
        this.jml_suara2=hasil.jml_suara2;
        this.jml_suara3=hasil.jml_suara3;
        this.jml_suara4=hasil.jml_suara4;
        this.jml_suara5=hasil.jml_suara5;
        this.jml_suara6=hasil.jml_suara6;
        this.persen0=hasil.persen0;
        this.persen1=hasil.persen1;
        this.persen2=hasil.persen2;
        this.persen3=hasil.persen3;
        this.persen4=hasil.persen4;
        this.persen5=hasil.persen5;
        this.persen6=hasil.persen6;
        this.nama_calon0=hasil.nama_calon0;
        this.nama_calon1=hasil.nama_calon1;
        this.nama_calon2=hasil.nama_calon2;
        this.nama_calon3=hasil.nama_calon3;
        this.nama_calon4=hasil.nama_calon4;
        this.nama_calon5=hasil.nama_calon5;
        this.nama_calon6=hasil.nama_calon6;
      
      });


      
    },

    loadTotalAll() {
      const baseURI = this.$settings.endPoint + "data/totalall";

      return this.$http.get(baseURI).then((response) => {
        const hasil = response.data.hasil;
        this.total_dtp=hasil.total_dtp;
        this.total_rusak=hasil.total_rusak;
        this.total_suara=hasil.total_suara
        
      });
    },
  },
  created() {
    setInterval(this.loadTotalAll, 1000);
    setInterval(this.loadCalonSatuan, 1000);
   
  },
  mounted() {

    this.loadTotalAll();
    this.loadCalonSatuan();
    // console.log(this.featchCalon);
    //                setInterval(() => {
    //                     // console.log(this.featchCalon);
                      
                        
    //                }, 1000);
          

    
    
    // axios
    //   .get("https://www.themealdb.com/api/json/v1/1/categories.php")
    //   .then(response => {
    //     this.meals = response.data.categories;
    //   })
    //   .catch(err => {
    //     console.log(err);
    //   });
  },
};
</script>