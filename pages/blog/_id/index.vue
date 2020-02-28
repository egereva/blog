<template>
  <div class="wrapper-content wrapper-content--fixed">
    <section class="post">
      <div class="container">
        <post :post="post" />
        <comments :comments="comments" />
        <newComment :postId="$route.params.id"/>
      </div>
    </section>
  </div>
</template>


<script>
  import axios from 'axios'

  import post from '@/components/Blog/Post.vue'
  import newComment from '@/components/Comments/NewComment.vue'
  import comments from '@/components/Comments/Comments.vue'

  export default {
    components: {
      post,
      comments,
      newComment
    },
    async asyncData (context) {
      let [post, comments] = await Promise.all([
        axios.get(`https://blog-nuxt-38e13.firebaseio.com/posts/${context.params.id}.json`),
        axios.get(`https://blog-nuxt-38e13.firebaseio.com/comments.json`)
      ])

      if (!comments.data) {
        comments.data = {};
      }

      // first variant

      // let commentsArray = [],
      //     commentsArrayRes = []
      //
      // Object.keys(comments.data).forEach(key => {
      //   commentsArray.push(comments.data[key])
      // })
      //
      // for(let i = 0; i < commentsArray.length; i++) {
      //   if (commentsArray[i].postId === context.params.id && commentsArray[i].publish) {
      //     commentsArrayRes.push(commentsArray[i])
      //   }
      // }

      // second variant

      let commentsArrayRes = Object.values(comments.data).filter(comment => (comment.postId === context.params.id) && comment.publish)

      return {
        post: post.data,
        comments: commentsArrayRes
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
