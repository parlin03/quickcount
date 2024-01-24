<template>
  <div>
    <b-navbar toggleable="lg" type="light" variant="info">
      <b-container>
        <b-navbar-brand href="#"
          >Quick Count 2024 : Pemilihan Calon Legislatif Makassar B Dapil II Sulsel  | <b-badge variant="info" style="font-size:large">{{timestamp}}</b-badge>
          </b-navbar-brand
        >
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <b-collapse id="nav-collapse" is-nav>
          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto"> </b-navbar-nav>
        </b-collapse>
      </b-container>
    </b-navbar>
  </div>
</template>
<script>
export default {
  data() {
    return {
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
      const dateTime = date + " " + time;
      this.timestamp = dateTime;
    },
  },
};
</script>
