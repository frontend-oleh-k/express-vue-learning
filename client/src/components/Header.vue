<template>
  <v-app-bar
    app
    color="primary"
    dark
    hide-on-scroll
    class="wrapper"
  >
    <div class="header_wrapper">
      <router-link to="/">
        <p class="logo">
          <i class="fab fa-500px"></i>
          <span>hopify</span>
        </p>
      </router-link>
      <v-spacer />
      <span>
        <v-btn icon color="white">
          <v-icon>fa-shopping-cart</v-icon>
        </v-btn>
      </span>
    </div>
  </v-app-bar>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
  .logo {
    display: flex;
    font-size: 2.5rem;
    align-items: center;
    margin-bottom: 0;
    color: #fff;
    span {
      font-size: 2rem;
    }
  }
  .header_wrapper {
    display: flex;
    justify-content: space-between;
    width: 100%;
    align-items: center;
  }
</style>
