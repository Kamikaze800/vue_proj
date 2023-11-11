<template>
  <div class="post">
    <div>
      <div><strong>Hазвание:</strong> {{ post.title }}</div>
      <div><strong>Oписание:</strong> {{ post.body }}</div>
    </div>
    <div class='post_btns'>
      <my-button
      @click="$emit('remove', post)">Delete</my-button>
    </div>
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";

export default {
  name: "PostItem",
  components: {MyButton},
  props: {
    post: {
      type: Object,
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
  align-items: center;
  display: flex;
  justify-content: space-between;
}
</style>