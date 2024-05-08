<template>
  <div>
    <form @submit.prevent>
      <h3>Название поста</h3>
      <input
          v-model="post.title"
          class="input"
          type="text"
          placeholder="Название"
      >
      <input
          v-model="post.body"
          class="input"
          type="text"
          placeholder="Описание"
      >
      <button
          class="btn"
          @click="createPost"
      >
        Создать
      </button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: '',
        body: '',
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: '',
      }
    },
  }
}
</script>

<style scoped>
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