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
        console.log('post added')
        console.log(post)
      }
    }
  }
</script>
