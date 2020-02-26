<template>
  <div class="wrapper-content wrapper-content--fixed">
    <promo/>
    <Intro title = "My lasts posts:" />
    <PostsList :posts="postsLoaded"/>
    <contacts/>
  </div>
</template>

<script>
  import promo from '@/components/Promo.vue'
  import contacts from '@/components/Contacts.vue'

  export default {
    components: {
      promo,
      contacts
    },
    asyncData (context) {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve({
            postsLoaded: [
              {
                id: 1,
                title: '1 post',
                descr: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut',
                img: 'https://lawnuk.com/wp-content/uploads/2016/08/sprogs-dogs.jpg'
              },
            ]
          })
        }, 1500)
      })
        .then(data => {
          return data
        })
        .catch(e => {
          context.error(e)
        })
    },
    data () {
      return {
        posts: [
          // {
          //   id: 1,
          //   title: '1 post',
          //   descr: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut',
          //   img: 'https://lawnuk.com/wp-content/uploads/2016/08/sprogs-dogs.jpg'
          // },
        ]
      }
    },
    created () {

    }
  }
</script>

