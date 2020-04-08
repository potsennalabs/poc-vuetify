<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <div @click="visible = true">
          <v-rating v-model="rating" empty-icon="mdi-star" color="#f9b653" background-color="#e4e4e6" readonly></v-rating>
        </div>
      </v-col>
      <v-col cols="12">
        <div class="skull-container primary--text">
          <v-rating
            v-model="skullRating"
            color="#63a1d5"
            background-color="#e4e4e6"
            full-icon="mdi-skull"
            empty-icon="mdi-skull"
          ></v-rating>
          
          <v-icon color="primary">
            mdi-close
          </v-icon>
          <div>{{ skullRating }}</div>
        </div>
      </v-col>
    </v-row>
    <com-b v-model="visible" />
  </v-container>
</template>

<script>
  // import ComA from './comA';
  import ComB from './comB';

  export default {
    name: 'HelloWorld',
    components: { ComB },
    data() {
      return {
        rating: 4,
        skullRating: 3,
        visible: false
      }
    }
  }
</script>

<style scoped>
  .skull-container {
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>
