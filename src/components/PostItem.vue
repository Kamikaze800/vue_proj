<template>
 <div class="post">
    <div><strong>Hазвание:</strong> {{ post.title }}</div>
    <div><strong>Oписание:</strong> {{ post.body }}</div>
  </div>
</template>

<script>
export default {
  name: "PostItem",
  props: {
    post: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>

</style>