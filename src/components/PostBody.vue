<template>
  <div class="wrap">
    {{ title }}
    <div>
      评论数:{{ numberComment}}
    </div>
    
  </div>
</template>

<script>
export default {
  name:'PostBody',
  props:['title'],
  computed:{
    numberComment(){
      return this.$store.state.comment.all.length
    }
  }
}
</script>

<style scoped>
.wrap {
    background-color: #fff;
    width: 400px;
    min-height: 30vh;
    margin: 20px auto;
    box-shadow: 0 2px 2px rgba(0, 0, 0, 0.5);
  }
</style>
