<template>
  <b-container fluid class="screensaver_container">
    <b-row  class="cancelling" ref="skip">
      <nuxt-link id="blink" to="/ru/glavnaya">
        <h4 class="skip">Пропустить заставку / Skip splash screen</h4>
      </nuxt-link>
    </b-row>
    <b-row >
       <b-col lg="12" class="screen_container" >
         <b-row  class="mt-5">
           <b-col  class="mt-5 screen_column" lg="12">
             <div class="logo_wrapper">
               <div class="logo_animation">
                 <img ref="logo" class="logo" src="../static/logo_screensaver_with_border.png"/>
               </div>
             </div>
             <div ref="slogan_shadow" >
               <div ref="slogan" class="slogan_wrapper">
                 <h1 ref="_the" class="slogan_even">The</h1>
                 <h1 ref="magic" class="slogan">magic</h1>
                 <h1 ref="force" class="slogan_even">force</h1>
                 <h1 ref="of" class="slogan">of</h1>
                 <h1 ref="the" class="slogan_even">the</h1>
                 <h1 ref="music" class="slogan">music</h1>
               </div>
             </div>
           </b-col>
         </b-row>
         <b-row ref="langs">
           <b-col lg="6" md="6" sm="6" cols="12" class="langs">
             <nuxt-link to="/ru/glavnaya">
               <div class="langs_button_left">
                 <p>Русская версия</p>
                 <img class="langs_icon" src='../static/russia_flags_flag_17058.png' />
               </div>
             </nuxt-link>
           </b-col>
           <b-col lg="6" md="6" sm="6" cols="12"  class="langs">
             <nuxt-link to="/en/mainPage">
               <div class="langs_button_right">
                 <img class="langs_icon" src='../static/united_kingdom_flags_flag_17079.png' />
                 <p>English version</p>
               </div>
             </nuxt-link>
             <nuxt-link to="/en/mainPage">
               <div class="langs_button_right_responsive">
                 <p>English version</p>
                 <img class="langs_icon" src='../static/united_kingdom_flags_flag_17079.png' />
               </div>
             </nuxt-link>
           </b-col>
         </b-row>
       </b-col>
    </b-row>
  </b-container>
</template>

<script>

  import { TimelineLite } from "gsap";

    export default {
        name: "ScreenSaver",
        scrollToTop: true,
        components: {

        },
      mounted() {

          const { logo, slogan, _the, force, the, slogan_shadow, langs, skip } = this.$refs
          const tl = new TimelineLite()

          const width = document.body.clientWidth
          let y = null

          if (process.client) {
            if(width <= 319) {
              y = "-650rem"
            } else if(width >= 320 && width <= 369) {
              y = "-650rem"
            } else if(width >= 370 && width <= 577) {
              y = "-580rem"
            } else if(width >= 578 && width <= 767) {
              y = "-550rem"
            } else if(width >= 768 && width <= 1023) {
              y = "-530rem"
            } else if(width >= 1024 && width <= 1280) {
              y = "-450rem"
            } else {
              y = "-500rem"
            }
          }

          tl.from(logo, 1.5, { opacity: 0 , scale: 0, ease: Bounce.easeOut, delay: 1})
            .from(slogan, 1, { opacity: 0, ease: Power4.easeInOut, x: -150})
            .from(_the, 0.3 , { opacity: 0, ease: Bounce.easeInOut, x: 100 })
            .from(force, 0.3 , {  opacity: 0, ease: Bounce.easeInOut, x: 100 })
            .from(the, 0.3 , { opacity: 0, ease: Bounce.easeInOut, x: 100 })
            .to(slogan, 1, { opacity: 1, scale: 1, ease: Power1.easeOut, y: y})
            .to(slogan_shadow, 0.5, { textShadow: "0px 0px 30px rgba(255, 255, 255, 1)" })
            .to(slogan_shadow, 0.5, { textShadow: "none" })
            .from(langs, 1.5, { opacity: 0 , y:100 })
            .to(langs, 0.5, { textShadow: "0px 0px 30px rgba(255, 255, 255, 1)" })
            .to(langs, 0.5, { textShadow: "none" })
            .to(skip, 0.5, { animation: "none", opacity: 0 })


      },
      methods: {

      }
    }
</script>

<style scoped>

  .cancelling {
    display: flex;
    flex-direction: row;
    justify-content: center;
    color: #ffffff !important;
    font-family: 'Candara', sans-serif;
    text-transform: uppercase;
    padding-top: 40px;
  }

  .skip {
    text-align: center;
  }

  #blink {
    -webkit-animation: blink 1s linear infinite;
    animation: blink 1s linear infinite;
  }
  @-webkit-keyframes blink {
    0% { color: #ffffff; }
    50% { color: rgba(34, 34, 34, 0); }
    100% { color: #ffffff; }
  }
  @keyframes blink {
    0% { color: #ffffff; }
    50% { color: rgba(34, 34, 34, 0); }
    100% { color: #ffffff; }
  }

  .screen_container {
    height:100%;
    margin-top:2%;
  }

  .logo {
    width: 400px;
    height: 400px;

  }

  .logo_animation {

    height: 100%;
  }

  .logo_wrapper {
    display: flex;
    flex-direction: row;
    justify-content: center;
    width: 100%;
    margin-top: 3%;
  }

  .langs {
    text-align: center;
    color: #fff !important;
    font-family: 'Bahnschrift', sans-serif;
    text-transform: uppercase;
     padding-top: 1%;
    font-weight: 300;
    font-size: 1.5rem;
  }

  .langs p {
    margin: auto 0;
  }

  .langs_icon {
    width: 50px;
    height: 50px;
    margin: 0 20px;
  }

  .langs_button_left {
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    color:#ffffff;
    text-decoration: none;
  }

  .langs_button_left:hover {
    text-shadow: 0px 0px 30px rgba(255, 255, 255, 1);
    cursor: pointer;
  }

  .langs_button_left:active {
    text-shadow: 0px 0px 30px rgba(255, 255, 255, 1);
    cursor: pointer;
    color: #006fb5;
  }

  .langs_button_right {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    color:#ffffff;
    text-decoration: none;
  }

  .langs_button_right_responsive {
    display: none;
  }

  .langs_button_right:hover {
    text-shadow: 0px 0px 30px rgba(255, 255, 255, 1);
    cursor: pointer;
  }

  .langs_button_right:active {
    text-shadow: 0px 0px 30px rgba(255, 255, 255, 1);
    cursor: pointer;
    color: #006fb5;
  }

  .langs_button_right_responsive:hover {
    text-shadow: 0px 0px 30px rgba(255, 255, 255, 1);
    cursor: pointer;
  }

  .langs_button_right_responsive:active {
    text-shadow: 0px 0px 30px rgba(255, 255, 255, 1);
    cursor: pointer;
    color: #006fb5;
  }

  .slogan  {
    display: inline;
    text-align: center;
    color: #fff !important;
    font-family: 'Venus Rising', sans-serif;
    text-transform: uppercase;
    margin-left: 20px;
    min-height: 250px;
  }

  .slogan_even  {
    display: inline;
    text-align: center;
    color: #7F828B !important;
    font-family: 'Venus Rising', sans-serif;
    text-transform: uppercase;
    margin-left: 20px;
    min-height: 250px;
  }

  .slogan_wrapper {
    text-align: center;
  }

  .screensaver_container {
    height: 100vh;
    z-index: 10;
  }

  .screen_column {
    height: 100%;
  }

  @media (max-width: 319px) {
    .logo_wrapper {
      margin-top: 65%;
    }

    .screen_container {
      margin-top: 10%;
    }

    .langs_button_left, .langs_button_right_responsive {
      display: flex;
      flex-direction: row;
      justify-content: center;
      color:#ffffff;
      text-decoration: none;
    }

    .langs_button_right {
      display: none;
    }
  }

  @media (min-width: 320px) and (max-width: 577px) {
    .logo_wrapper {
      margin-top: 55%;
    }

    .langs_button_left, .langs_button_right_responsive {
      display: flex;
      flex-direction: row;
      justify-content: center;
    }

    .langs_button_right {
      display: none;
    }
  }

  @media (min-width: 578px) and (max-width: 767px) {
    .screen_container {
      margin-top: 5%;
    }

    .logo_wrapper {
      margin-top: 7%;
    }
  }

  @media (min-width: 768px) and (max-width: 1028px) {
    .logo_wrapper {
      margin-top: 10%;
    }

    .screen_container {
      margin-top: 5%;
    }
  }
</style>
