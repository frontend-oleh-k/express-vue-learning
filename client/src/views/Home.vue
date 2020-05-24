<template>
  <div class="main">
    <v-container>
      <h1 class="display-2">Main items</h1>
      <div class="grid">
        <v-card
          v-for="n in 4"
          :key="n"
          class="grid__item"
        >
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
            height="194"
          ></v-img>
          <v-card-title>
            Card title
          </v-card-title>
          <v-card-text>
            Visit ten places on our planet that are undergoing the biggest changes today.
          </v-card-text>

          <v-card-actions>
            <v-btn
              text
              color="deep-purple accent-4"
            >
              Buy for $33.33
            </v-btn>
            <v-spacer></v-spacer>
            <v-btn icon>
              <v-icon>mdi-heart</v-icon>
            </v-btn>
            <v-btn icon>
              <v-icon>mdi-share-variant</v-icon>
            </v-btn>
          </v-card-actions>
        </v-card>
      </div>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
  },
};
</script>

<style lang="scss" scoped>
  .main {
    margin-top: 40px;

    h1 {
      text-align: center;
    }
  }
  .grid {
    display: flex;
    flex-wrap: wrap;
  }
  .grid__item {
    max-width: 29%;
    margin: 2%;
  }
</style>
