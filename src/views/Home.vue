<template>
  <div class="home">
    <!--<p class="display-2 font-weight-bold text-center grey--text text--darken-3">Software Developer & Database Designer, Developer</p>
    -->
    <v-row class="mt-12" align="center"
      justify="center">
        <v-img :src="require('../assets/logo.png')" max-height="471" max-width="400"></v-img>
    </v-row>
    <!-- Header introduction section -->
    <v-row align="center" justify="center" class="mt-12 py-12 px-5 primary">
      <div class="introduction px-3" >
        <div class="introduction-title display-2 pb-12">
          <span>Hey, I'm Mantas.</span><br/>
          <span>I can solve</span><span class="cross-out grey--text text--lighten-1"> all some one of your</span><span> problems, ok?</span><br/> 
        </div>
        <div class="introduction-content display-1">
          <span>I design, build & sometimes maintain Software & Databases</span><br/>
          <p class="mt-3">Have a project, idea or problem you'd like to discuss?</p>
          <span>Let's chat <a class="grey--text text--lighten-1" href="mailto:Baltakisdev@gmail.com">Baltakisdev@gmail.com</a></span>
        </div>
      </div>
    </v-row>
    <!--Skills section-->
    <v-row align="center" justify="center" class="skills">
      <v-col cols="10" md="10" lg="8" xl="6">
        <v-card raised class="elevation-24">
          <v-row class="px-12 pt-10" align="start" justify="center" >
            <v-col cols="12" md="4" align="center" class="skill" v-for="skill in skills" :key="skill.title">
              <v-icon color="primary" class="skill-icon">{{skill.icon}}</v-icon>
              <p class="headline mt-5">{{skill.title}}</p>
              <p class="pt-6">{{skill.languagesTitle}}:</p>
              <p>{{skill.languages}}</p>
              <p class="pt-12">Tools I currently use: </p>
              <v-row class="skill-logo" v-for="tool in skill.tools" :key="tool" align="center" justify="center">
                <v-col cols="2" md="4" lg="2" xl="1" class="px-0 py-2">
                <v-img :src="require('../assets/' + tool + '.svg')" height="30" width="35" contain>
                </v-img>
                </v-col>
                <v-col cols="3" md="5" lg="3" xl="4" class="px-0 py-2">
                  <span align="baseline">{{tool}}</span>
                </v-col>
              </v-row>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>

export default {
  data() {
    return {
      skills: [
        { 
          icon: 'mdi-code-tags',
          title: 'Front-End Developer',
          languagesTitle: 'Languages I speak',
          languages: 'HTML, CSS, Sass, JS',
          tools: [
            'Bootstrap',
            'Bulma',
            'Github',
            'VSC',
            'VueJs',
            'Vuetify'
          ]
        },
        { 
          icon: 'mdi-settings mdi-spin',
          title: 'Back-End Developer',
          languagesTitle: 'Jargon I mastered',
          languages: 'PHP, C#, Python',
          tools: [
            'Firebase',
            'Heroku',
            'Laravel',
            'npm',
            'Apache',
            'Cmder'
          ]
        },
        { 
          icon: 'mdi-database',
          title: 'Database Developer',
          languagesTitle: 'Ways I store data',
          languages: 'MySql, NoSql',
          tools: [
            'DBeaver',
            'MySql Workbench',
            'Visio',
            'phpMyAdmin'
          ]
        }
      ]
    }
  }
};
</script>

 <style>
 .home {
   margin-top: 120px;
 }
 .cross-out {
   text-decoration: line-through;
 }
 a {
   text-decoration: none;
 }
 .introduction {
   padding-bottom: 200px;
 }
 .skills {
   margin-top: -150px;
 }
 .skill-icon {
   font-size: 70px !important;
 }
 @media only screen and (max-width: 960px) {
  .skill {
    border-bottom: 1px solid #BDBDBD;
   }
 }
 </style>