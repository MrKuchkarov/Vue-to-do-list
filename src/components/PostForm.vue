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
      <my-button
          class="btn"
          style="align-self: flex-end"
          @click="createPost"
      >
        Создать
      </my-button>
    </form>
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";

export default {
  components: {MyButton},
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
</style>