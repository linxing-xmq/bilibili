<template>
  <div class="home">
      

  </div>
</template>

<script>
export default {
   data(){
       return{
           categorylist:[],
           active:0
       }
   },
   created(){
       
   },
   watch: {

   },
   methods:{
    
   async getCategory(){
     const res= await this.$http.get("/category");
     res.data.forEach((item) => {
         item.page=0;
         item.pagesize=10;
         item.loading=false;
         item.finshed=false;
         item.list=[];
     });
     this.categorylist=res.data;
     
   },
   selectArticle(){
       le
   }


   }





}
</script>

<style>

</style>