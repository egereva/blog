<template>
  <newPostForm @submit="onSubmit" />
</template>

<script>
  import newPostForm from '@/components/Admin/newPostForm.vue'

  export default {
    layout: 'admin',
    components: {
      newPostForm
    },
    methods: {
      onSubmit (post) {
        this.$store.dispatch('addPost', post)
          .then(() => {
            this.$router.push('/admin')
          })
      }
    }
  }
</script>
