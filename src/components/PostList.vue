<template>
  <div>
    <h3>Список пользователей</h3>
    <post-item v-for="post in posts" :post="post"/>
  </div>
</template>

<script>
import PostItem from "@/components/PostItem.vue";

export default {
  name: "PostList",
  components: {PostItem},
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