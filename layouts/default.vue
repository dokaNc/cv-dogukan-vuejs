<template>
  <v-app dark>
    <v-card class="mx-2" flat tile>
      <v-toolbar color="#121212" flat>
        <v-app-bar-nav-icon
          v-on:click="handleDrawer(); circle.mdi = 'mdi-circle-outline'">
        </v-app-bar-nav-icon>
        <v-spacer></v-spacer>
        <v-btn icon>
          <v-icon>mdi-translate</v-icon>
        </v-btn>
        <v-btn icon>
          <v-icon>mdi-theme-light-dark</v-icon>
        </v-btn>
      </v-toolbar>
    </v-card>

    <v-card>
      <v-navigation-drawer color="#121212" v-model="drawer" width="300" fixed app>
        <v-list width="95%">
          <v-list-item class="ma-3">
            <v-list-item-avatar>
              <v-img src="https://media-exp1.licdn.com/dms/image/C4D03AQF-R3zQi14OPQ/profile-displayphoto-shrink_400_400/0/1636639571630?e=1669852800&v=beta&t=GMqToQjegdfAWqKqfrST0wYm0jalViDY_1xyUVy5C4Q"></v-img>
            </v-list-item-avatar>
            <v-list-item-title class="custom-list-item-title">DOGUKAN</v-list-item-title>
            <v-list-item-icon>
              <v-icon
                :color="circle.color" 
                v-on:click="handleDrawer(); circle.mdi = 'mdi-circle'">
                {{ circle.mdi }}
              </v-icon>
            </v-list-item-icon>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list width="85%">
          <v-subheader>Découvrez moi</v-subheader>
          <v-list-item 
              class="rounded-r-xl" 
              v-for="(item, index) in items" 
              :key="index" 
              :to="item.to"
              link
            >
            <v-list-item-icon class="ml-3 mr-4">
              <v-icon dense>{{ item.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-content>
                <v-list-item-title class="ma-0 pa-0">{{item.title}}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
    </v-card>
    <v-main>
        <Nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      drawer: true,
      mini: true,
      circle: { mdi: 'mdi-circle-outline', color: '#9836F4' },
      items: [
        { title: 'Un peu de moi', icon: 'mdi-account-outline', to: '/' },
        { title: 'Skills', icon: 'mdi-head-snowflake-outline', to: '/skill' },
        { title: 'Expériences', icon: 'mdi-briefcase-outline', to: '/experience' },
        { title: 'Occupations', icon: 'mdi-piano', to: '/hobie' },
        { title: 'Contactez-moi', icon: 'mdi-card-account-mail-outline', to: '/contact' },
      ]
    }
  },

  methods: {
    handleDrawer() {
      return this.drawer = !this.drawer;
    },

    mobile() {
      return this.drawer = false;
    }
  },

  computed: {
  }
}
</script>

<style lang="css" scoped>
  /* GLOBAL */
  * {
    font-family: "Montserrat", sans-serif;
    font-weight: 300;
  }
  /* NAVIGATION DRAWER */
  .v-navigation-drawer {
    box-shadow: 0px 0px 10px 0px #0b0b0b;
    transition-duration: 0.8s;
  }
  .v-navigation-drawer >>> .v-navigation-drawer__border {
    display: none
  }

  /* LIST ITEM */
  .custom-list-item-title {
    font-weight: 700;
    font-size: 20px;
  }
  .theme--dark.v-list-item:hover::before {
    border-radius: 0 50px 50px 0;
  }
  .v-list-item--link:before {
    transition: none;
  }
  .theme--dark.v-list-item--active:hover::before, .theme--dark.v-list-item--active::before {
    background: linear-gradient(90deg, #121212 0%, #9836f4 60%);
    border-radius: 0 50px 50px 0;
    opacity: 0.5;
  }
  </style>