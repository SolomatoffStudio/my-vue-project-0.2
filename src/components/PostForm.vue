<template>
  <form @submit.prevent>
    <h4>Create a post</h4>
    <my-input
        v-model="post.title"
        type="text"
        placeholder="Название"/>
    <my-input
        v-model="post.body"
        type="text"
        placeholder="Описание"/>
    <my-button
        style="align-self: flex-end; margin-top: 15px"
        @click="createPostOnForm"
    >
      Create
    </my-button>
  </form>
</template>

<script>
export default {
  name: "PostForm",
  data() {
    return {
      post: {
        title: '',
        body: ''
      }
    }
  },
  methods: {
    createPostOnForm() {
      this.post.id = Date.now();
      this.$emit('create',this.post)
      this.post = {
        title: '',
        body: ''
      }
    },
  }
}
</script>

<style scoped>

</style>