<template>
  <div>
      <van-uploader :after-read="afterRead" />
      
      <van-uploader :src="imgSrc" multiple />
  </div>
</template>

<script>
export default {
    data() {
        return {
            imgSrc: ''
        }
    },
    methods: {
        async afterRead(file) {
             console.log(file);
            const fromdata = new FormData();
            fromdata.append('file', file.file);
            const res =  await this.$http.post('/upload',fromdata);
            this.imgSrc = res.data.url;
        }
    }
}
</script>

<style>

</style>