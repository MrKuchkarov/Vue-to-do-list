<template>
  <div class="app">
    <post-form @create="createPost"/>
    <post-list :posts="posts"/>
  </div>
</template>

<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";
  export default {
    components: {
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
      }
    },
    methods: {
      createPost(post) {
        this.posts.push(post)
      },
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