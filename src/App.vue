<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <v-app-bar-nav-icon @click="drawer = !drawer" />

      <v-spacer />
    </v-app-bar>

    <template>
      <v-navigation-drawer
        v-model="drawer"
        dark
        app
        :src="require('@/assets/navi.jpeg')"
      >
        <template v-slot:img="props">
          <v-img
            :gradient="gradient"
            v-bind="props"
          >
            f
          </v-img>
        </template>
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title class="text-h6">
              Application
            </v-list-item-title>
            <v-list-item-subtitle>
              subtext
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-divider />

        <v-list
          dense
          nav
        >
          <v-list-item
            v-for="item in items"
            :key="item.title"
            link
            :to="item.to"
            active-class="primary"
            class="py-3"
          >
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
    </template>

    <v-main>
      <v-container
        fluid
      >
        <router-view />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  data: () => ({
    drawer: false,
    gradient: 'rgba(0, 0, 0, .7), rgba(0, 0, 0, .7)',
    items: [
      { title: 'Dashboard', icon: 'mdi-view-dashboard', to: '/' },
      { title: 'GridSystem', icon: 'mdi-image', to: '/grid-system' },
      { title: 'Breakpoints', icon: 'mdi-image', to: '/breakpoints' },
      { title: 'GridListPage', icon: 'mdi-image', to: '/grid-list-page' },
      { title: 'Typography', icon: 'mdi-image', to: '/typography' },
      { title: 'Buttons', icon: 'mdi-image', to: '/buttons' },
      { title: 'Forms', icon: 'mdi-image', to: '/forms' },
      { title: 'Tables', icon: 'mdi-image', to: '/tables' },
      { title: 'Icons', icon: 'mdi-image', to: '/icons' },

    ],
    right: null,
  }),
};
</script>