<template>
  <div class="wrapper-content wrapper-content--fixed">
    <section class="about">
      <div class="container">
        <h1 class="title">About my blog: </h1>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
        </p>
        <Intro title="Lorem ipsum dolor sit amet"/>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
        </p>
        <img src="@/assets/img/designer.jpeg" alt="">
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
        </p>
      </div>
    </section>
  </div>
</template>

<script>
  export default {
    head() {
      let title = 'About My SSR Blog!',
        descr = 'About My SSR Blog! With Nuxt.js!',
        type = 'site'

      return {
        title: title,
        meta: [
          { hid: 'description', name: 'description', content: descr},
          { hid: 'og:description', name: 'og:description', content: descr},
          { hid: 'og:title', name: 'og:title', content: title},
          { hid: 'og:type', name: 'og:type', content: type}
        ]
      }
    },
  }
</script>

<style lang="scss">
  .about {
    text-align: center;

    p {
      margin-bottom: 10px;
    }

  }
</style>
