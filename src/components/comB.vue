<template>
  <div class="text-xs-center">
    <v-bottom-sheet :value="value" @input="onClose">
      <v-list>
        <v-subheader><b>Give me the Stars</b></v-subheader>
        <v-list-item
          v-for="row in tiles"
          :key="row.title"
        >
        <v-list-item-content>
          <v-list-item-title>{{ row.title }}</v-list-item-title>
        </v-list-item-content>
          <v-list-item-action>
            <div v-show="row.status" @click="row.status = !row.status">
              <v-btn icon >
                <v-icon color="#f9b653">mdi-star</v-icon>
              </v-btn>
            <div style="font-size: 10px;">I like this!</div>
            </div>
            <v-btn icon v-show="!row.status" @click="row.status = !row.status">
              <v-icon color="#f9b653">mdi-star-outline</v-icon>
            </v-btn>
          </v-list-item-action>
          
        </v-list-item>
      </v-list>
    </v-bottom-sheet>
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: Boolean,
      default: false
    }
  },
  data: () => ({
    sheet: false,
    tiles: [
      { status: false, title: 'Show knowledge in a particular skill' },
      { status: false, title: 'Helping out another team member' },
      { status: false, title: 'Make it happen - Working late or hard to get things done' },
      { status: false, title: 'Positive attitude' },
      { status: false, title: 'Cute' }
    ],
  }),
  methods: {
    onClose() {
      this.$emit('input', false);
    },
  }
}
</script>

<style scoped>
  .v-list {
    border-top-left-radius: 16px;
    border-top-right-radius: 16px;
  }

  .v-subheader {
    justify-content: center;
  }

  .v-list-item__action{
    width: 70px;
    justify-content: center;
    align-items: center;
  }
</style>