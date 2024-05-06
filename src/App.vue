<template>
  <div class="app">
      <form>
        <h3>Название поста</h3>
        <input class="input" type="text" placeholder="Название"></input>
        <input class="input" type="text" placeholder="Описание"></input>
        <button class="btn">Создать</button>
      </form>
   <div class="post" v-for="post in posts">
     <div><strong>Название:</strong>{{ post.title }}</div>
     <div><strong>Описание:</strong>{{ post.body }}</div>
   </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        posts: [
          {id: 1, title: 'JavaScript', body: 'Описание поста'},
          {id: 2, title: 'PHP', body: 'Описание поста'},
          {id: 3, title: 'Python', body: 'Описание поста'},
          {id: 4, title: 'Vue', body: 'Описание поста'},
        ]
      }
    },
    methods: {

    }
  }
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  padding: 20px;
}
.post {
  padding: 15px;
  border: 2px solid darkgreen;
  margin-top: 15px;
}
form {
  display: flex;
  flex-direction: column;
}
.input {
  width: 100%;
  border: 2px solid darkgreen;
  padding: 10px 15px;
  margin-top: 15px;
}
.btn {
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: darkgreen;
  border: 1px solid darkgreen;

}
</style>