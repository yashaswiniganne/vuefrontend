<template>
  <div>
    <SchoolDetail :schools="schools"/>
  </div>
</template>

<script>


import SchoolDetail from "@/components/SchoolDetail";
export default {
  name: 'SchoolList',
  components: {
    SchoolDetail
  },
  props:{
    schools: Array,
  },
}
</script>

