<template>
  <PostsList :admin=true :posts="posts"/>
</template>

<script>
  export default {
    layout: 'admin',
    data () {
      return {
        posts: [
          {
            id: 1,
            title: '1 post',
            descr: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut',
            img: 'https://lawnuk.com/wp-content/uploads/2016/08/sprogs-dogs.jpg'
          },
          {
            id: 2,
            title: '2 post',
            descr: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut',
            img: 'https://iheartdogs.com/wp-content/uploads/2017/09/Brite-Bite-0021-2.jpg'
          },
          {
            id: 3,
            title: '3 post',
            descr: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut',
            img: 'https://avatars.mds.yandex.net/get-pdb/964669/905e9ab5-f170-42a8-beea-ed37400c3883/s1200'
          }
        ]
      }
    }
  }
</script>

