<template>
  <div class="app">
  <form @submit.prevent>
    <h4>Создание поста</h4>
    <input v-bind:title="title" @input="title = $event.target.value" class="input" type="text" placeholder="Название">
    <input v-bind:title="body" @input="inputBody" class="input" type="text" placeholder="Oпиcaниe">
    <button class="btn" @click="createPost">Coздать</button>
  </form>
  <div class="post" v-for="post in posts">
    <div><strong>Hазвание:</strong> {{ post.title }}</div>
    <div><strong>Oписание:</strong> {{ post.body }}</div>
  </div>
  <div>
    <button @click="addlike">Likes: {{ likes }}</button>
    <button @click="adddislike">Dislikes: {{ dislikes }}</button>
  </div>
    </div>
</template>

<script>
export default {
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
    createPost() {
      const newPost = {
        id: Date.now(),
        title: this.title,
        body: this.body,
      }
      this.posts.push(newPost);
      this.title = '';
      this.body = '';
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
.app{
  padding: 20px;
}
form {
  display: flex;
  flex-direction: column;
}
.input {
width: 100%;
border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}
.btn {
  align-self: flex-end;
  margin-top: 15px;
  padding: 10px 15px;
  background: none;
  color: teal;
}
.post {
  border: 1px solid teal;
  padding: 15px;
  margin-top: 15px;
}
</style>