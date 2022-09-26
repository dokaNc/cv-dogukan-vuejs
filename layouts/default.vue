<template>
  <v-app dark>
    <v-app-bar color="transparent" hide-on-scroll flat app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
    </v-app-bar>
      <v-navigation-drawer v-model="drawer" absolute temporary>
        <v-list nav dense>
          <v-list-item-group v-model="group">
            <v-list-item v-for="(item, i) in items" :key="i" link>
              <v-list-item-title>
                  {{item.title}}
              </v-list-item-title>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </v-navigation-drawer>
    <v-main>
        <Nuxt />
    </v-main>
    <v-footer app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      drawer: false,
      group: null,
      items: [
        {
          title: 'Accueil',
          to: '/'
        },
      ],
    }
  },

  watch: {
      group () {
        this.drawer = false
      },
    },
}
</script>

<style scoped>
  /* .theme--dark.v-application {
    background-color: #3c4649;
  } */
  .theme--dark.v-navigation-drawer {
    background-color: #191919;
  } 
  </style>