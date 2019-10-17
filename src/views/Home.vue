<template>
  <div class="home">
    <!-- <h1 class="display-2 font-weight-bold text-center grey--text text--darken-3">Software Developer & Database Designer, Developer</h1> -->
    
    
     <v-row class="mt-md-12" align="center"
      justify="center">
        <v-img :src="require('../assets/logoPurple.png')" max-height="421" max-width="350" contain class="headerLogo"></v-img>
    </v-row>
    <v-row align="center" justify="center" class="header-top-image">
      <v-img :src="require('../assets/header_top.svg')" max-width="700px" contain></v-img>
    </v-row>
    <!-- Header introduction section -->
    <v-row align="center" justify="center" class=" py-12 px-5 primary white--text">
        <div class="introduction px-3" >
          <div class="introduction-title display-2 pb-12">
            <p><span>Hey, I'm Mantas.</span><br/>
            <span>I can solve</span><span class="cross-out "> all some one of your</span><span> problems, ok?</span></p>
          </div>
          <div class="introduction-content display-1">
            <span>I design, build & sometimes maintain Software & Databases</span><br/>
            <p class="mt-3">Have a project, idea or problem you'd like to discuss?</p>
            <span>Let's chat <a class="grey--text text--darken-4" href="mailto:Baltakisdev@gmail.com">Baltakisdev@gmail.com</a></span>
          </div>
        </div>
    </v-row>
    <!--Skills section-->
    <v-row align="center" justify="center" class="skills">
      <v-col cols="10" md="10" lg="9" xl="6">
        <v-card raised class="elevation-24">
          <v-row class="px-12 pt-10" align="start" justify="center" >
            <v-col cols="12" md="4" align="center" class="skill pb-12" v-for="skill in skills" :key="skill.title">
              <v-icon color="primary" class="skill-icon">{{skill.icon}}</v-icon>
              <p class="headline mt-5">{{skill.title}}</p>
              <p class="pt-6">{{skill.languagesTitle}}:</p>
              <p>{{skill.languages}}</p>
              <p class="pt-12">Current Toolkit: </p>
              <v-row class="skill-logo" v-for="tool in skill.tools" :key="tool" align="center" justify="center">
                <v-col cols="4" sm="2" md="4" lg="2" xl="1" class="px-0 py-2">
                <v-img :src="require('../assets/' + tool + '.svg')" height="30" max-width="50" contain>
                </v-img>
                </v-col>
                <v-col cols="7" sm="4" md="5" lg="3" xl="4" class="px-0 py-2">
                  <span align="baseline">{{tool}}</span>
                </v-col>
              </v-row>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
    <!--Recent Work section -->
    <v-row align="center" justify="center" class="mt-12 py-12 px-5 ">
      <div class="text-center recentWorkHeader">
        <p class="display-2">My Recent Work</p><br/>
        <p class="subheading">Here are a few recent projects. Want to see more?</p><br/>
        <p class="subheading ">Visit my <a href="https://github.com/Mantasbl" target="_blank" color="primary">Github</a> page</p>
      </div>
    </v-row>
    <v-row class="recentWork" justify="center" align="center">
      <v-col cols="10" md="10" lg="9" xl="6">
        <v-row justify="center">
          <v-col cols="12" md="6" lg="4" v-for="project in projects" :key="project.title" class="project">
            <v-hover>
              <template v-slot:default="{ hover }">
                <v-card class="mx-auto" max-width="400">
                  <v-img :src="require('../assets/Work/'+ project.title +'.png')" max-height="250px" ></v-img>
                  <v-fade-transition>
                        <v-overlay class="work px-8" v-if="hover" align="center" absolute color="primary" opacity="0.8">
                          <p class="subheading">{{project.title}}</p>
                          <v-chip v-for="skill in project.skills" :key="skill" class="ma-1 project-chip" color="grey darken-4" label>{{skill}}</v-chip>
                          <br/>
                          <br/>
                          <v-btn class="ma-1" color="grey darken-4" v-if="project.link != '' " rounded :href="project.link" target="_blank">Website</v-btn>
                          <v-btn fab color="grey darken-4" :href="project.github" target="_blank">
                            <v-icon large>mdi-github-circle</v-icon>
                          </v-btn>
                        </v-overlay>
                  </v-fade-transition>
                </v-card>
              </template>
            </v-hover>
          </v-col>
        </v-row>
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
          title: 'Front-End Development',
          languagesTitle: 'Languages I speak',
          languages: 'HTML, CSS, Sass, JS',
          tools: [
            'Bootstrap',
            'Bulma',
            'Material Design',
            'VSC',
            'VueJs',
            'Vuetify',
            'jQuery'
          ]
        },
        { 
          icon: 'mdi-settings',
          title: 'Back-End Development',
          languagesTitle: 'Jargon I mastered',
          languages: 'PHP, C#, Python',
          tools: [
            'Firebase',
            'Github',
            'Heroku',
            'Laravel',
            'npm',
            'Apache',
            'WordPress'
          ]
        },
        { 
          icon: 'mdi-database',
          title: 'Database Development',
          languagesTitle: 'Ways I store data',
          languages: 'MySql, NoSql',
          tools: [
            'DBeaver',
            'MySql Workbench',
            'Visio',
            'phpMyAdmin'
          ]
        }
      ],
      projects: [
        {
          title: 'Todo',
          skills: [
            'HTML',
            'CSS',
            'VueJs',
            'Vuetify',
            'Firebase',
            'Material Design'
          ],
          link: 'https://todo.baltakisdev.com',
          github: 'https://github.com/Mantasbl/Todo-vuejs',
        },
        {
          title: 'Portfolio',
          skills: [
            'HTML',
            'CSS',
            'VueJs',
            'Vuetify',
            'Material Design',
          ],
          link: '',
          github: 'https://github.com/Mantasbl/portfolio',
        },
        {
          title: 'Patatap',
          skills: [
            'HTML',
            'CSS',
            'Paper.js',
            'Howler.js',
            'HTML5 Canvas'
          ],
          link: 'http://baltakisdev.com/patatap',
          github: 'https://github.com/Mantasbl/PatatapClone',
        },
        {
          title: 'MyPuppyDen',
          skills: [
            'HTML',
            'CSS',
            'Laravel',
            'Bulma',
            'Heroku',
            'MySql'
          ],
          link: 'https://mypuppyden.herokuapp.com',
          github: 'https://github.com/Mantasbl/MyPuppyDen',
        },
        {
          title: 'GymBro',
          skills: [
            'HTML',
            'CSS',
            'jQuery',
            'PHP',
            'localStorage',
            'HTML5 Canvas'
          ],
          link: 'http://baltakisdev.com/gymbro/',
          github: 'https://github.com/Mantasbl/GymBro',
        },
        {
          title: 'EcommerceDB',
          skills: [
            'PHP',
            'MySql',
            'Visio',
            'Data Dictionary',
            'ERD',
          ],
          link: '',
          github: 'https://github.com/Mantasbl/Ecommerce_database',
        },
      ],
    }
  },
  methods: {
  }
}
</script>

 <style>
 .home {
   margin-top: 60px;
 }
 .header-top-image {
   margin-top: 80px;
 }
 .cross-out {
   text-decoration: line-through;
 }
 a {
   text-decoration: none;
 }
 .introduction{
   padding: 100px 0 200px 0;
 }
 .skills{
   margin-top: -150px;
 }
 .skill-icon {
   font-size: 70px !important;
 }
 .project-chip{
   pointer-events:none;
 }
 @media only screen and (max-width: 960px) {
  .skill {
    border-bottom: 1px solid #BDBDBD;
   }
   .home {
     margin-top: 20px;
   }
   .headerLogo {
     height:300px;
     width: 250px;
   }
   .introduction-title {
     font-size: 2rem !important;
   }
 }
 </style>