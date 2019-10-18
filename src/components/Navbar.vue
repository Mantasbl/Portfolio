<template>
  <nav>
    <v-row align="center" justify="center">
      <v-col cols="11" sm="10" md="10" lg="9" xl="6">
        <v-toolbar flat color="#fafafa" class="mb-12">
          <v-toolbar-title class=""><img :src="require('../assets/logoNamePrimary.svg')" height="20" /></v-toolbar-title>
          <v-spacer></v-spacer>
          <div class="hidden-sm-and-down">
            <v-btn class="mx-2" color="transparent" large depressed>
                <v-icon large color="primary">mdi-email</v-icon>
                <span class="ml-2"><a href="mailto:Baltakisdev@gmail.com" class="black--text">BaltakisDev@gmail.com</a></span>
            </v-btn>
            <br class="d-flex d-md-none"/>
            <v-tooltip bottom v-for="icon in icons" :key="icon.icon" >
              <template v-slot:activator="{ on }">
                <v-btn class="mx-2" fab dark large color="primary" outlined :href="icon.href" v-on="on" target="_blank">
                    <v-icon large>{{icon.icon}}</v-icon>
                </v-btn>
              </template>
              <span>{{icon.title}}</span>
            </v-tooltip>
          </div>
          <v-menu offset-y >
                <template v-slot:activator="{ on }">
                    <v-btn rounded color="primary" outlined class="hidden-md-and-up" v-on="on">Say Hello</v-btn>
                </template>
                <v-list>
                    <v-list-item>
                      <v-btn class="mx-2 my-4" color="transparent" large depressed>
                          <v-icon large color="primary">mdi-email</v-icon>
                          <span class="ml-2"><a href="mailto:Baltakisdev@gmail.com" class="black--text">BaltakisDev@gmail.com</a></span>
                      </v-btn>
                    </v-list-item>
                    <v-list-item class="mx-8">
                      <v-btn class="mx-2" v-for="icon in icons" :key="icon.title" fab dark large color="primary" outlined :href="icon.href" target="_blank">
                          <v-icon large>{{icon.icon}}</v-icon>
                      </v-btn>
                    </v-list-item>
                </v-list>
            </v-menu>
        </v-toolbar>
      </v-col>
    </v-row>
  </nav>
</template>
<script>
  export default {
    data() {
      return {
        icons: [
          {
            icon: "mdi-github-circle",
            href: "https://github.com/Mantasbl",
            title: "Github"
          },
          {
            icon: "mdi-linkedin-box",
            href: "https://www.linkedin.com/in/mantas-baltakis/",
            title: "LinkedIn"
          },
          {
            icon: "mdi-facebook-messenger",
            href: "https://www.m.me/mantas.baltakis",
            title: "Messenger"
          }
        ]
      }
    }
  }
</script>
<style></style>