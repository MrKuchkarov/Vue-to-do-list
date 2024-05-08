<template>
  <div class="app">
    <h1>Страница с постами</h1>
    <my-button @click="showDialog">Создать пользователя</my-button>
    <my-dialog v-model:show="dialogVisible">
      <post-form @create="createPost"/>
    </my-dialog>
    <post-list :posts="posts" @remove="removePost"/>
  </div>
</template>

<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";
import MyButton from "@/components/UI/MyButton.vue";

  export default {
    components: {
      MyButton,
      PostForm,
      PostList
    },
    data() {
      return {
        posts: [
          {id: 1, title: 'JavaScript', body: 'Описание поста'},
          {id: 2, title: 'PHP', body: 'Описание поста'},
          {id: 3, title: 'Python', body: 'Описание поста'},
          {id: 4, title: 'Vue', body: 'Описание поста'},
        ],
        dialogVisible: false
      }
    },
    methods: {
      createPost(post) {
        this.posts.push(post)
      },
      removePost(post) {
        this.posts = this.posts.filter(p => p.id !== post.id)
      },
      showDialog() {
        this.dialogVisible = true;
      }
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

form {
  display: flex;
  flex-direction: column;
}
</style>