<template>
    <v-row align="center" justify="center" class="white--text primary mt-12 py-12">
        <v-col cols="10" md="10" lg="9" xl="6">
                    <h2 class="display-1 text-center">Say Hello</h2><br/>
                    <div class="BottonNavSocial" align="center">
                        <v-btn class="mx-2 mb-6 mb-md-0" dark large color="primary" depressed>
                            <v-icon large>mdi-email</v-icon>
                            <span class="ml-2"><a href="mailto:Baltakisdev@gmail.com" class="white--text">BaltakisDev@gmail.com</a></span>
                        </v-btn>
                        <br class="d-flex d-md-none"/>
                        <v-tooltip top v-for="icon in icons" :key="icon.icon" >
                            <template v-slot:activator="{ on }">
                            <v-btn class="mx-2" fab dark large outlined :href="icon.href" v-on="on" target="_blank">
                                <v-icon large>{{icon.icon}}</v-icon>
                            </v-btn>
                            </template>
                            <span>{{icon.title}}</span>
                        </v-tooltip>
                    </div>
                <v-row align="center" justify="center" class="mt-12">
                    <p>BaltakisDev <v-icon color="white">mdi-copyright</v-icon> 2019</p>
                </v-row>
        </v-col>
    </v-row>
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

<style>
</style>