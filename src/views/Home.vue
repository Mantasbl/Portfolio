<template>
  <div class="home">
    <!-- <h1 class="display-2 font-weight-bold text-center grey--text text--darken-3">Software Developer & Database Designer, Developer</h1> -->
    
    
     <v-row class="mt-md-12" align="center"
      justify="center">
        <v-img :src="require('../assets/logo.png')" max-height="350" max-width="300" contain class="headerLogo"></v-img>
    </v-row>
    <v-row align="center" justify="center" >
      <div>
        <v-img :src="require('../assets/header_top.png')" class="header-top-image" max-width="700px" contain></v-img>
      </div>
    </v-row>
    <!-- Header introduction section -->
    <v-row align="center" justify="center" class="py-12 px-5 introduction-row">
        <div class="introduction px-3" >
          <div class="display-2 pb-12">
            <p><span class="introduction-title">Hey, I'm Mantas.</span><br/>
              <span class="introduction-content">
                <span>I can solve</span>
                  <span class="strike">
                    <span class="fade-in one"> all</span>
                    <span class="fade-in two"> some</span>
                    <span class="fade-in three"> one of your</span>
                  </span>
                <span> problems, ok?</span>
              </span>
            </p>
          </div>
          <div class="introduction-content display-1">
            <span>I design, build & sometimes maintain Software & Databases</span>
            <p class="mt-3">Have a project, idea or problem you'd like to discuss?</p>
            <span>Let's chat <a color="primary" href="mailto:Baltakisdev@gmail.com">Baltakisdev@gmail.com</a></span>
          </div>
        </div>
    </v-row>
    <!--Skills section-->
    <v-row align="center" justify="center" class="skills">
      <v-col cols="10" md="10" lg="9" xl="6">
        <v-card>
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
      isActive: false,
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
    crossOut() {
    setTimeout(function(){
      isActive = true;
    }, 2000);
    } 
  },
  
}
</script>

 <style>
 /* Base styling */
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
 .introduction-row {
   border-top: 3px solid #E03400;
   border-bottom: 3px solid #E03400;
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
 /* Animations */


@keyframes strike{
  0%   { width : 0; }
  100% { width: 100%; }
}
.strike {
  position: relative;
}
.strike::after {
  content: ' ';
  position: absolute;
  top: 50%;
  left: 0;
  width: 100%;
  height: 3px;
  background: black;
  animation-name: strike;
  animation-duration: 5s;
  animation-timing-function: linear;
  animation-iteration-count: 1;
  animation-fill-mode: forwards; 
}

@-webkit-keyframes fadeIn { from { opacity:0; } to { opacity:1; } }
@-moz-keyframes fadeIn { from { opacity:0; } to { opacity:1; } }
@keyframes fadeIn { from { opacity:0; } to { opacity:1; } }

.fade-in {
    opacity:0;  /* make things invisible upon start */
    -webkit-animation:fadeIn ease-in 1;  /* call our keyframe named fadeIn, use animattion ease-in and repeat it only 1 time */
    -moz-animation:fadeIn ease-in 1;
    animation:fadeIn ease-in 1;

    -webkit-animation-fill-mode:forwards;  /* this makes sure that after animation is done we remain at the last keyframe value (opacity: 1)*/
    -moz-animation-fill-mode:forwards;
    animation-fill-mode:forwards;

    -webkit-animation-duration:1.5s;
    -moz-animation-duration:1.5s;
    animation-duration:1.5s;
}
.fade-in.one {
  -webkit-animation-delay: 0.6s;
  -moz-animation-delay: 0.6s;
  animation-delay: 0.6s;
}

.fade-in.two {
  -webkit-animation-delay: 1.2s;
  -moz-animation-delay:1.2s;
  animation-delay: 1.2s;
}
.fade-in.three {
  -webkit-animation-delay: 1.8s;
  -moz-animation-delay: 1.8s;
  animation-delay: 1.8s;
}
.fade-in.four {
  -webkit-animation-delay: 2.4s;
  -moz-animation-delay: 2.4s;
  animation-delay: 2.4s;
}
 /* Media Queries */
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
   .header-top-image{
     width:350px;
   }
   .introduction-title {
     font-size: 50px !important;
  }
  .introduction-content {
    font-size: 34px !important;
  }
 }
@media only screen and (max-width: 600px) {
.introduction-title {
font-size: 40px !important;
}
.introduction-content {
font-size: 24px !important;
}
}
 </style>