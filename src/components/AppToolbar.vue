<template>
  <div>
    <v-toolbar color="indigo" dark>
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <router-link to="/">
        <v-toolbar-title class="white--text">Vuetify Project</v-toolbar-title>
      </router-link>
      <!--v-spacer moves what is before it to the right and waht is below it to the left-->
      <v-spacer></v-spacer>
      <v-badge left>
      <span slot="badge">6</span>
      <v-icon
        large
        color="white"
      >
        fa fa-bell
      </v-icon>
    </v-badge>
      <div class="hidden-sm-and-down">
        <router-link to="/about">
          <v-btn flat>About</v-btn>
        </router-link>
        <router-link to="/contact">
          <v-btn flat>Contact</v-btn>
        </router-link>
        <router-link to="/login">
          <v-btn flat>Login</v-btn>
        </router-link>
      </div>
    </v-toolbar>

    <div class="hidden-md-and-up">
      <v-navigation-drawer
        v-model="drawer"
        absolute
        temporary
      >
        <v-list class="pa-1">
          <v-list-tile avatar>
            <v-list-tile-avatar>
              <img src="https://randomuser.me/api/portraits/men/85.jpg">
            </v-list-tile-avatar>

            <v-list-tile-content>
              <v-list-tile-title>John Leider</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>

        <v-list class="pt-0" dense>
          <v-divider></v-divider>

          <v-list-tile
            v-for="item in items"
            :key="item.title"
          >
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>

            <v-list-tile-content>
              <v-list-tile-title>{{ item.title }}</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-navigation-drawer>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      drawer: null,
      items: [
        { title: 'Home', icon: 'dashboard' },
        { title: 'About', icon: 'question_answer' }
      ]
    }
  }
}
</script>
<style scoped>
</style>
