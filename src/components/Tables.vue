<template>
  <div style="font-size: 0.45rem;">
    <b-table style="max-width: 100%; text-align: right; " striped hover :items="items"></b-table>
  </div>
</template>

<script>

export default ({
    name: 'TableComponent',
    data() {
    return {
      items: [],
    
    }
  },

  methods: {
    loadHasilTps() {
      const baseURI = this.$settings.endPoint + "data/hasiltps";

      return this.$http.get(baseURI).then((response) => {
        const hasil = response.data.hasil;
        this.items = [];
        hasil.forEach((value) => {

            var data={
              kecamatan:value.namakec,
              total_dpt:value.jml_dpt,
              suara_partai:value.jml_suara_paslon0,
              suara_1:value.jml_suara_paslon1,
              suara_2:value.jml_suara_paslon2,
              suara_3:value.jml_suara_paslon3,
              suara_4:value.jml_suara_paslon4,
              suara_5:value.jml_suara_paslon5,
              suara_6:value.jml_suara_paslon6,
              // tidak_sah:value.jml_rusak,
              jumlah_suara:value.jml_suara,
            }

           
            this.items.push(data);
        });

      });
    },

   
  },
  created() {
    setInterval(this.loadHasilTps, 1000);
  },
  mounted() {
    this.loadHasilTps();
    

  },

})
</script>
