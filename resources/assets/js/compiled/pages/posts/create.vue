<template>
  <div class="col-lg-6 col-lg-offset-3">
    <form @submit.prevent="apiCreatePost">
      <legend>New Post</legend>
      <div class="form-group">
        <input type="text" v-model="post.title" placeholder="Title" class="form-control">
      </div>
      <div class="form-group">
        <textarea id="" cols="30" rows="6" v-model="post.body" class="form-control"></textarea>
      </div>
      <div class="form-group">
        <button class="btn btn-lg btn-primary btn-block" type="submit">
          Save
        </button>
      </div>
    </form>
  </div>
</template>

<script>
  export default {

    name: 'post-editor',

    data () {
      return {
        post: {
          title: null,
          body: null
        }
      };
    },

    methods: {
      apiCreatePost() {
        let that = this
        client({ path: 'posts', entity: this.post }).then(
          response => console.log(response),
          response => console.log(response)
        )
      }
    }
  };
</script>

<style lang="css" scoped>
</style>
