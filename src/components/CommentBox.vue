<template>
  <div class="wrap">
    <div v-for="comment in reversedComments" :key="comment.id">
      {{ comment.body }}
    </div>
    <input type="text" v-model="msg"><button @click="submitComment">发送</button>
  </div>
</template>

<script>
export default {
  name:'CommentBox',
  data:()=>({
    msg:'',
  }),
  computed:{
    comments() { 
      return this.$store.state.comment.all
    },
    reversedComments(){
      return this.comments.slice().reverse()
    }
  },
  methods:{
    submitComment(){
      console.log(this.msg)
      let comment = {
        body: this.msg
      }
      this.$store.dispatch({ type: 'addComment', comment })
      this.msg=''
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
