<template>
  <div class="app">
    <post-form @create="createPost"/>
    <post-list v-bind:posts="posts"/>

    <div>
      <button @click="addlike">Likes: {{ likes }}</button>
      <button @click="adddislike">Dislikes: {{ dislikes }}</button>
    </div>
  </div>
</template>

<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";

export default {
  components: {PostForm, PostList},
  data() {
    return {
      posts: [
        {id: 1, title: 'Javacript', body: 'Oписание поста'},
        {id: 2, title: 'Javacript 2', body: 'Onисание поста 2'},
        {id: 3, title: 'Javacript 3', body: 'Oписание поста 3'},
      ],
      title: '',
      body: '',
      likes: 0,
      dislikes: 0,
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
    inputTitle(event) {
      this.title = event.target.value;
    },
    inputBody(event) {
      this.body = event.target.value;
    },
    addlike() {
      this.likes++
    },
    adddislike() {
      this.dislikes++
    }
  }

}
</script>

<style scoped> /*scoped говорит: стили применяются только для этого компонента*/
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.app {
  padding: 20px;
}


</style>