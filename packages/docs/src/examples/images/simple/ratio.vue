<template>
  <v-container fluid>
    <v-slider v-model="width" min="200" max="500" step="1"></v-slider>
    <v-navigation-drawer
      :width="width"
      :value="true"
      stateless
    >
      <v-img :aspect-ratio="16/9" src="https://cdn.vuetifyjs.com/images/parallax/material.jpg">
        <v-row class="lightbox white--text pa-2 fill-height">
          <div class="flex-grow-1"></div>
          <v-col class="shrink">
            <div class="subheading">Jonathan Lee</div>
            <div class="body-1">heyfromjonathan@gmail.com</div>
          </v-col>
        </v-row>
      </v-img>

      <v-list>
        <template v-for="(item, i) in items">
          <v-divider v-if="item.divider" :key="i"></v-divider>
          <v-list-item v-else :key="item.title" @click>
            <v-list-item-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </template>
      </v-list>
    </v-navigation-drawer>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      width: 300,
      items: [
        { icon: 'inbox', title: 'Inbox' },
        { icon: 'star', title: 'Starred' },
        { icon: 'send', title: 'Sent mail' },
        { icon: 'drafts', title: 'Drafts' },
        { divider: true },
        { icon: 'mail', title: 'All mail' },
        { icon: 'delete', title: 'Trash' },
        { icon: 'error', title: 'Spam' },
      ],
    }),
  }
</script>

<style scoped>
  .v-navigation-drawer {
    transition: none !important;
  }

  .lightbox {
    box-shadow: 0 0 20px inset rgba(0, 0, 0, 0.2);
    background-image: linear-gradient(to top, rgba(0, 0, 0, 0.4) 0%, transparent 72px);
  }
</style>
