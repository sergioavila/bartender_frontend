<template>
  <v-layout>
  <v-toolbar dark>
    <v-toolbar-side-icon  @click.stop="drawer = !drawer"></v-toolbar-side-icon>
    <v-spacer></v-spacer>

    <v-btn icon>
      <v-icon>search</v-icon>
    </v-btn>
    <v-btn icon>
      <v-icon>favorite</v-icon>
    </v-btn>
  </v-toolbar>

  <v-navigation-drawer
  v-model="drawer"
  absolute
  dark
  temporary
  >
  <v-list class="pa-1">

    <v-list-tile avatar tag="div">
      <v-list-tile-avatar>
        <img src="https://randomuser.me/api/portraits/men/3.jpg">
      </v-list-tile-avatar>

      <v-list-tile-content>
        <v-list-tile-title>Sergio Ávila</v-list-tile-title>
      </v-list-tile-content>

    </v-list-tile>
  </v-list>

  <v-list class="pt-0" dense>
    <v-divider light></v-divider>

    <v-list-tile  v-for="item in items"
          :key="item.title">
      <v-list-tile-action>
        <v-icon>{{ item.icon }}</v-icon>
      </v-list-tile-action>
      <router-link :to="`${item.url}`" class="dropdown-item">
        <v-list-tile-content>
          <v-list-tile-title>{{ item.title }}</v-list-tile-title>
        </v-list-tile-content>
      </router-link>

    </v-list-tile>

  </v-list>
</v-navigation-drawer>
</v-layout>
</template>
<script>
export default {
  data () {
    return {
      drawer: null,
      items: [
        { title: 'Home', icon: 'home', url: '/' },
        { title: 'Login', icon: 'person', url: '/login'},
        { title: 'Favorites', icon: 'favorite', url: '/favorites'},
        { title: 'Categories', icon: 'folder', url: '/categories'}
      ],
      right: null
    }
  }
}
</script>
