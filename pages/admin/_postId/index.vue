<template>
  <newPostForm
      :postEdit="post"
      @submit="onSubmit" />
</template>

<script>
  import axios from 'axios'
  import newPostForm from '@/components/Admin/newPostForm.vue'

  export default {
    layout: 'admin',
    components: {
      newPostForm
    },
    asyncData (context) {
        return axios.get(`https://blog-nuxt-38e13.firebaseio.com/posts/${context.params.postId}.json`)
          .then(res => {
            return {
              post: {...res.data, id: context.params.postId}
            }
          })
          .catch(e => context.error(e))
    },
    methods: {
      onSubmit (post) {
        this.$store.dispatch('editPost', post)
          .then(() => {
            this.$router.push('/admin')
          })
      }
    }
  }
</script>
