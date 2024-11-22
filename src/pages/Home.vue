<template>
<div>
  <h2>Test data from Flask API(Running with QCH)</h2>
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
    this.$axios.get("http://awsus-devtsrv-01/flask/students").then(response =>{
      this.Alldata=response.data
    })
    .catch(error => {
            console.log(error)
        })
  }
}
}
</script>
