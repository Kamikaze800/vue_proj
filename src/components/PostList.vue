<template>
 <div class="post" v-for="post in posts">
    <div><strong>Hазвание:</strong> {{ post.title }}</div>
    <div><strong>Oписание:</strong> {{ post.body }}</div>
  </div>
</template>

<script>
export default {
  name: "PostList",
  props: {
    posts:{
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
.post {
  border: 1px solid teal;
  padding: 15px;
  margin-top: 15px;
}
</style>