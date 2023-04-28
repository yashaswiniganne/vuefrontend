<template>
  <div class="container">
  <header>
    <HeaderBar title="Top Universities in the World "/>
  </header>
  <p> According to QS World University Rankings 2023, these are the top 10 universities in the world. </p>
  <SchoolList :schools="schools"/>
  <footer>
    <FooterBar content="&copy; Copyright 2023"/>
  </footer>
  </div>
</template>

<script>

import HeaderBar from "@/components/HeaderBar";
import SchoolList from "@/components/SchoolList";
import FooterBar from "@/components/FooterBar";

export default {
  name: 'App',
  components: {
    HeaderBar,
    SchoolList,
    FooterBar
  },
  data(){
    return{
      schools: [],
    };
  },
  async created(){
    this.schools = await this.fetchData();
  },
  methods:{
    async fetchData(){
      const res = await fetch("http://localhost:5959/api")
      const data = await res.json()
      console.log(data)
      return data.schools
    },
  },
};
</script>

<style scoped>
/**{*/
/*  margin:0;*/
/*  padding:0;*/
/*  box-sizing: border-box;*/
/*}*/

.container{
  background: #7395AE;
}

p{
  text-align: center;
  color: white;
}
header{
  text-align: center;
  background: #7395AE;
  color: white;
  padding-top: 20px;
}
footer{
  text-align: center;
  background: #7395AE;
  color: white;
  padding: 20px;
  margin-top: 50px;
}
</style>
