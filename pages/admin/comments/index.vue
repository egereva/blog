<template>
  <client-only>
    <commentTable :thead="['Name', 'Text', 'Status', 'Change Status', 'Delete']">
      <tbody slot="tbody">
        <tr v-for="comment in comments" :key="comment.id">
          <td>
            <span>{{ comment.name }}</span>
          </td>
          <td>
            <span>{{ comment.text }}</span>
          </td>
          <td>
            <span v-if="comment.publish" class="status true"> Publish </span>
            <span v-else class="status false"> Hiden </span>
          </td>
          <td>
            <span @click="changeComment(comment)" class="link"> Change Status </span>
          </td>
          <td>
            <span @click="deleteComment(comment.id)" class="link"> Delete </span>
          </td>
        </tr>
      </tbody>
    </commentTable>
  </client-only>
</template>

<script>
  import axios from 'axios'
  import commentTable from "@/components/Admin/CommentTable";

  export default {
    layout: 'admin',
    components: {
      commentTable
    },
    data () {
      return {
        comments: [],
      }
    },
    mounted() {
      this.loadComments()
    },
    methods: {
      loadComments () {
        axios.get('https://blog-nuxt-38e13.firebaseio.com/comments.json')
          .then(res => {
            let commentsArray = []
            Object.keys(res.data).forEach(key => {
              const comment = res.data[key]
              commentsArray.push({...comment, id: key})
            })

            this.comments = commentsArray
          })
      },
      changeComment (comment) {
        comment.publish = !comment.publish

        axios
          .put(`https://blog-nuxt-38e13.firebaseio.com/comments/${comment.id}.json`, comment)
      },
      deleteComment (id) {
        axios
          .delete(`https://blog-nuxt-38e13.firebaseio.com/comments/${id}.json`)
            .then(res => {
              this.loadComments()
            })
      },

    }
  }
</script>
