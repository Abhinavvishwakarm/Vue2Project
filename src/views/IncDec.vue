<template>
  <v-app>
    <v-main>
      <v-container>
        <v-card class="mx-auto" max-width="400">
          <v-card-title>
            <h1>{{ count }}</h1>
          </v-card-title>
          <v-card-actions>
            <v-btn class="btnIncrement" @click="increment">Increment</v-btn>
          </v-card-actions>
           <v-card-actions>
            <v-btn class="btnDecrement" @click="decrement">Decrement</v-btn>
          </v-card-actions>
        </v-card>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  computed: {
    count() {
      return this.$store.getters.getCount;
    }
  },
  methods: {
    increment() {
      this.$store.dispatch('increment');
    },
    decrement() {
      this.$store.dispatch('decrement')
    }
  }
};
</script>

<style>
/* Add your styles here */
.btnIncrement {
    margin-right: 10px;
    color: red;
    font-size: x-large;
}
.btnDecrement {
    margin-left: 10px;
    color: blue;
    font-size: x-large;
}
</style>