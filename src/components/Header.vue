<template>
<div>
    <v-app-bar
      class="hidden-md-and-up"
      color="indigo"
      dark
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title>CEAF</v-toolbar-title>
    </v-app-bar>

    <v-navigation-drawer
      :permanent="$vuetify.breakpoint.mdOnly"
      v-model="drawer"
      app
    >
      <h1 id="logo"><a href="#"><span>CE</span><span>AF</span></a></h1>
      <v-list dense>
        <v-list-item v-for="item in items"
          :key="item.title"
          :to="item.link" link>
          <v-list-item-action>
            <v-icon>{{item.icon}}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title class="font-15">{{item.title}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
        <v-footer absolute>
          <v-row>
            <v-btn v-for="item in icons" :key="item.icons" :to="item.link" link target="_blank" class="mx-2 mb-4 mt-3" fab dark x-small color="black">
          <v-icon size="13px">{{ item.icons }}</v-icon>
                  </v-btn>
          </v-row>
          <p>{{ new Date().getFullYear() }} — CEAF</p>
          

        </v-footer>
    </v-navigation-drawer>

</div>
</template>

<script>
export default {
    name: 'Header',
    data() {
      return {
          drawer: null,
          items: [
              { title: 'Inicio', icon: 'mdi-home', link: '/' },
              { title: 'Acerca', icon: 'mdi-account', link: '/about' },
              { title: 'Trabajos', icon: 'mdi-briefcase', link: '/portafolio' },
              { title: 'Contacto', icon: 'mdi-email', link: '/contacto' },
                ],
          icons: [
              { icons: 'mdi-instagram', link: '//www.instagram.com/ichrisaf/'},
              { icons: 'mdi-facebook', link: '//www.facebook.com/iChristianArzate'},
              { icons: 'mdi-linkedin', link: '//www.linkedin.com/in/christian-arzate/'}
          ]
              }
          },
}

</script>

