<template>
  <div class="wrapper-content wrapper-content--fixed">
    <section class="post">
      <div class="container">
        <post :post="post" />
        <comments :comments="comments" />
        <newComment />
      </div>
    </section>
  </div>
</template>


<script>
  import post from '@/components/Blog/Post.vue'
  import newComment from '@/components/Comments/NewComment.vue'
  import comments from '@/components/Comments/Comments.vue'

  export default {
    components: {
      post,
      comments,
      newComment
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
        comments: [
          {
            name: 'Alex',
            text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit'
          },
          {
            name: 'Marina',
            text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit'
          }
        ]
      }
    }
  }
</script>

<style lang="scss">
  .post {
    max-width: 900px;
    margin: 0 auto;
  }

  .post-header {
    text-align: center;
    margin-bottom: 30px;
    img {
      max-width: 400px;
      margin-bottom: 16px;
    }
    p {
      color: #999999;
    }
  }

  .post-body {
    text-align: left;
  }

</style>
