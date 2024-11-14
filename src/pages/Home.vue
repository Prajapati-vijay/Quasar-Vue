<template>
<div>
  <h2>Test data from Fast API(Running with QCH)</h2>
  {{ Alldata }}
  </div>
</template>

<script>
export default {
  name:"Home",
data(){
  return{
    Alldata:{}
  }
},
created(){
this.getData()
console.log("Fun called")
},
methods:{
  getData(){
    this.$axios.get("http://djr.local/flask/students").then(response =>{
      this.Alldata=response.data
    })
    .catch(error => {
            console.log(error)
        })
  }
}
}
</script>
