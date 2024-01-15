<template>
     <b-table striped hover :items="items"></b-table>
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
              jml_dtp:value.jml_dtp,
              suara_partai:value.jml_suara_paslon0,
              caleg_1:value.jml_suara_paslon1,
              caleg_2:value.jml_suara_paslon2,
              caleg_3:value.jml_suara_paslon3,
              caleg_4:value.jml_suara_paslon4,
              caleg_5:value.jml_suara_paslon5,
              caleg_6:value.jml_suara_paslon6,
              jml_rusak:value.jml_rusak,
              jml_suara:value.jml_suara,
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
