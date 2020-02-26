<template>
  <section class="auth">
    <div class="container">
      <form @submit.prevent="onSubmit" class="auth-form">
        <AppInput type="email" v-model="user.email"> Login: </AppInput>
        <AppInput type="password" v-model="user.password"> Password: </AppInput>

        <div class="controls">
          <AppButton> Login! </AppButton>
        </div>
      </form>
    </div>
  </section>
</template>

<script>
  export default {
    data () {
      return {
        user: {
          email: '',
          password: ''
        }
      }
    },
    methods: {
      onSubmit () {
        // Reset
        this.user.email = ''
        this.user.password = ''
      }
    }
  }
</script>

<style lang="scss">
  .auth {
    text-align: center;
    margin-top: 100px;
  }
  .auth-form {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-direction: column;
    width: 100%;
    height: 40vh;

    input {
      min-width: 460px;
    }
  }
</style>
