<template>
  <v-app light>
    <v-navigation-drawer absolute temporary v-model="sideNave">
      <v-list>
        <v-list-tile v-for="item in menuItens" :key="item.title">
          <v-list-tile-action>
            <v-icon>{{item.icons}}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>{{item.title}}</v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar cliped-left dark class="primary" fixed app>
      <v-toolbar-side-icon @click.native.stop="sideNave= !sideNave" class="hidden-sm-and-up"></v-toolbar-side-icon>
      <v-toolbar-title>Armando A.</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-only">
        <v-btn flat v-for="item in menuItens" :key="item.title">
          <v-icon left>{{item.icons}}</v-icon>
          {{item.title}}
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-content>
      <router-view></router-view>
    </v-content>
    
    <v-footer  app>
      <span class="text-lg-center">&copy; Armando Almeida 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      sideNave: false,
      menuItens: [
        { icons: 'account_circle', title: 'About me' },
        { icons: 'work', title: 'Portifolio' },
        { icons: 'build', title: 'Skills' },
        { icons: 'contacts', title: 'Contact me' }
      ]
    }
  }
}
</script>
