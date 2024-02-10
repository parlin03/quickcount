<template>
  <div>
    <b-navbar type="light" variant="info" >
      <b-container>
        <b-navbar-brand href="#" style="text-align: center;"
          >
          
            <b-badge variant="info" style="font-size:1rem">{{datestamp}}<br>{{timestamp}}</b-badge>

          
          </b-navbar-brand
        >
        <!-- <b-navbar-toggle target="nav-collapse"></b-navbar-toggle> -->
        <b-collapse id="nav-collapse" is-nav class="d-flex justify-content-center">
      
          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto" style="text-align: center; font-weight: 600;"> 
          
          Calon Legislatif DPRD 2024 
          
          
          <br>
          Dapil Sulsel II (Makassar B)
          </b-navbar-nav>
      
        </b-collapse>
      </b-container>
    </b-navbar>
  </div>
</template>
<script>
export default {
  data() {
    return {
      datestamp: "",
      timestamp: ""
    };
  },
  created() {
    setInterval(this.getNow, 1000);
  },
  methods: {
    getNow() {
      const today = new Date();
      const getDate = ((today.getDate())>=10)? (today.getDate()):'0'+(today.getDate());
      const getMonth = ((today.getMonth()+1)>=10)? (today.getMonth()+1):'0'+(today.getMonth()+1);
      const getHours = ((today.getHours())>=10)? (today.getHours()):'0'+(today.getHours());
      const getMinutes = ((today.getMinutes())>=10)? (today.getMinutes()):'0'+(today.getMinutes());
      const getSeconds = ((today.getSeconds())>=10)? (today.getSeconds()):'0'+(today.getSeconds());
      // console.log(month);
      const date =
      getDate + "/" + getMonth + "/" + today.getFullYear();
        
      const time =
      getHours + ":" + getMinutes + ":" + getSeconds;
      // const dateTime = date + " " + time;
      this.datestamp = date;
      this.timestamp = time;
    },
  },
};
</script>
