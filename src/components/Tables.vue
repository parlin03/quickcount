<template>
     <b-table style="max-width: 20rem; text-align: right;" striped hover :items="items"></b-table>
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
              no_urut_1:value.jml_suara_paslon1,
              no_urut_2:value.jml_suara_paslon2,
              no_urut_3:value.jml_suara_paslon3,
              no_urut_4:value.jml_suara_paslon4,
              no_urut_5:value.jml_suara_paslon5,
              no_urut_6:value.jml_suara_paslon6,
              tidak_sah:value.jml_rusak,
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
