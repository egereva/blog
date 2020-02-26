<template>
  <newPostForm
      :postEdit="post"
      @submit="onSubmit" />
</template>

<script>
  import newPostForm from '@/components/Admin/newPostForm.vue'

  export default {
    layout: 'admin',
    components: {
      newPostForm
    },
    data () {
      return {
        post: {
          id: 1,
          title: '1 post',
          descr: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
          content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut',
          img: 'https://lawnuk.com/wp-content/uploads/2016/08/sprogs-dogs.jpg'
        },
      }
    },
    methods: {
      onSubmit (post) {
        console.log('post Editing')
        console.log(post)
      }
    }
  }
</script>
