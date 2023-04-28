<template>
  <div v-for="school in schools" :key="school.id" class="container">
    <img :src= "school.image"  :alt="school.name">
    <div class="content">
      <h3> {{school.name}} </h3>
      <div class="details">
        <p> <span> Rank: </span>  {{school.rank}}</p>
        <p> <span> Location: </span>  {{school.location}}</p>
        <p> <span> Founded in: </span>  {{school.foundedIn}}</p>
        <p> <span> Type: </span>  {{school.type}}</p>
        <p> <span> Graduation Rate: </span>  {{school.graduationRate}}</p>
      </div>
    </div>
  </div>
</template>

<script>


export default {
  name: 'SchoolDetail',
  props:{
    schools: Array,
  },
};
</script>

<style scoped>
.container{
  display: flex;
  background-color: whitesmoke;
  box-shadow: 0px 0px 10px 5px  rgba(100,100,100,0.1);
  padding: 20px 30px;
  border-radius: 5px;
  margin-top: 30px;
  margin-left: 20px;
  margin-right: 20px;
}

img{
  height: 190px;
  width: 220px;
  margin-top: 20px;
}

.content{
  line-height: 1.0;
  margin-left: 40px;
}

h3{
  color: #7395AE;
}

.details{
  margin-top: 10px;
}
span{
  font-weight: bold;
}



@media only screen and (max-width: 600px){
  .details{
    display: block;
  }
  img{
    margin-left: 90px;
  }
  .text {
    text-align: center;
    margin-left: 0px;
  }
}
@media only screen and (max-width: 420px){
  img{
    margin-left: 20px;
  }
}
</style>