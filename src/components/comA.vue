<template>
  <div class="text-xs-center">
      <v-btn
        color="purple"
        dark
        @click="sheet = true"
      >
        Click me
      </v-btn>
      <v-bottom-sheet v-model="sheet">
        <v-list>
          <v-subheader>Give me the Stars</v-subheader>
          <v-list-item
            v-for="tile in tiles"
            :key="tile.title"
            @click="sheet = false"
          >
            <v-list-item-avatar>
              <v-avatar size="32px" tile>
                <img
                  :src="`https://cdn.vuetifyjs.com/images/bottom-sheets/${tile.img}`"
                  :alt="tile.title"
                >
              </v-avatar>
            </v-list-item-avatar>
            <v-list-item-title>{{ tile.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-bottom-sheet>
    </div>
</template>

<script>
export default {
  data: () => ({
    sheet: false,
    tiles: [
      { img: 'keep.png', title: 'Keep' },
      { img: 'inbox.png', title: 'Inbox' },
      { img: 'hangouts.png', title: 'Hangouts' },
      { img: 'messenger.png', title: 'Messenger' },
      { img: 'google.png', title: 'Google+' }
    ],
  }),
}
</script>

<style scoped>
  .v-list {
    background-color: red !important;
  }
</style>