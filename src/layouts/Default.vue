<template>
  <v-app>
    <v-app-bar app color="purple accent-4" dark elevation="1">
      <v-app-bar-nav-icon @click.stop="sidebar = !sidebar"></v-app-bar-nav-icon>
      <v-spacer></v-spacer>
      <v-icon>mdi-account</v-icon>
    </v-app-bar>
    <v-navigation-drawer app v-model="sidebar" :mini-variant.sync="mini">
      <v-list dense color="purple accent-4" dark>
        <v-list-item>
          <v-list-item-action>
            <v-icon @click.stop="sidebar = !sidebar">mdi-chevron-left</v-icon>
          </v-list-item-action>  
          <v-list-item-title>
          <h3>Minha Lista de Tarefas</h3>
        </v-list-item-title>
        </v-list-item>
      </v-list>
      <v-list-item class="px-2" @click="mini = !mini">
        <v-list-item-avatar>
          <v-icon>mdi-account</v-icon>
        </v-list-item-avatar>
        <v-list-item-content> Beatriz de Arruda</v-list-item-content>
        <v-btn icon small><v-icon>mdi-chevron-left</v-icon></v-btn>
      </v-list-item>
      <v-divider></v-divider>
      <v-list>
        <v-list-item v-for="item of items" :key="item.title" link :to="item.to">
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>{{ item.title }}</v-list-item-content>
          </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <router-view></router-view>
    </v-main>
    <v-footer app class="py-3"><span class="caption">Minha Lista Vue &copy;</span></v-footer>
   
  </v-app>
</template>

<script>
export default {
  data() {
    return {
    sidebar: true,
    mini: false,
    items: [
      { title: "Home", icon: "mdi-account", to: "/"},
      { title: "Perfil", icon: "mdi-account-cog", to: "/perfil"},
       { title: "Login", icon: "mdi-exit-to-app", to: "/login"},
    ],
    };
  },
};
</script>

<style>

</style>
