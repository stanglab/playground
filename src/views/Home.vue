<template>
  <v-app id="sandbox" :dark="dark">
    <v-navigation-drawer
      :permanent="primaryDrawer.type"
      :clipped="primaryDrawer.clipped"
      :floating="primaryDrawer.floating"
      :mini-variant="primaryDrawer.mini"
      absolute
      overflow
      app
    >
    <v-toolbar flat class="transparent">
      <v-list class="pa-0">
        <v-list-tile avatar>
          <v-list-tile-avatar>
            <img src="@/assets/logo.png">
          </v-list-tile-avatar>

          <v-list-tile-content>
            <v-list-tile-title>John Leider</v-list-tile-title>
          </v-list-tile-content>

          <v-list-tile-action>
            <v-btn icon @click.stop="mini = !mini">
              <v-icon>chevron_left</v-icon>
            </v-btn>
          </v-list-tile-action>
        </v-list-tile>
      </v-list>
    </v-toolbar>

    <v-list class="pt-0" dense>
      <v-divider></v-divider>

      <v-list-tile v-for="item in items" :key="item.title" :to="item.link">
        <v-list-tile-action>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-tile-action>

        <v-list-tile-content>
          <v-list-tile-title>{{ item.title }}</v-list-tile-title>
        </v-list-tile-content>
      </v-list-tile>
    </v-list>
    </v-navigation-drawer>
    <v-content>
      <v-container fluid>
        <router-view />
      </v-container>
    </v-content>
    <v-footer :inset="footer.inset" app>
      <span class="px-3">Made with <v-icon small color="red">favorite</v-icon>&nbsp;<a href="http://https://github.com/stanglab/Tbinge">GitHub</a></span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    dark: true,
    primaryDrawer: {
      model: 'mini',
      type: 'permanent',
      clipped: true,
      floating: true,
      mini: true
    },
    items: [
      { title: 'Movies', icon: 'movie', link: '/movies' },
      { title: 'TV', icon: 'live_tv', link: '/tv' }
    ],
    footer: {
      inset: true
    }
  })
}
</script>

<style lang="sass">

</style>
