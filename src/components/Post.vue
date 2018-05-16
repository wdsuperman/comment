<template>
  <div class="post">
    <div class="upper">
      <PostBody :title="title" />
    </div>
    <div class="bottom">
      <CommentBox />
    </div>
  </div>
</template>

<script>
import CommentBox from "./CommentBox"
import PostBody from "./PostBody"
export default {
  name: 'Post',
  components:{
    PostBody,
    CommentBox
  },
  data:()=>({
    title:'React 技巧'
  })
}
</script>

<style scoped>
.post {
    display: flex;
    flex-direction: column;
    height: 100vh;
  }
  .upper {
    display: flex;
    background-color: #00bcd4;
  }
  .bottom {
    display: flex;
    flex-grow: 1;
    background-color: rgba(240, 240, 240, .5);
  }
</style>
