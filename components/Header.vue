<template>
  <div>
    <header >
      <div class="header_wrapper">
        <div ref="header">
          <div  class="header">
            <div class="rectangle">
              <div class="phone">+ 7 (812) 925-0-345</div>
              <div ref="link_w_t">
                <div class="messenger" ><a href="#" @click="win_dom.open('https://msng.link/tg/AlexanderJar')"><span class="icon"><img src="../static/telegram.png"/></span>
                  <span class="telegramm_link">Связаться</span></a></div>
                <div class="messenger" ><a href="#" @click="win_dom.open('https://api.whatsapp.com/send?phone=79816990947&text=%D0%94%D0%BE%D0%B1%D1%80%D1%8B%D0%B9%20%D0%B4%D0%B5%D0%BD%D1%8C%2C%20%D1%83%20%D0%BC%D0%B5%D0%BD%D1%8F%20%D0%B5%D1%81%D1%82%D1%8C%20%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B.%20%D0%9D%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D0%B0%20%D0%BA%D0%BE%D0%BD%D1%81%D1%83%D0%BB%D1%8C%D1%82%D0%B0%D1%86%D0%B8%D1%8F.')"><span class="icon"><img src="../static/whatsapp.png"/></span>
                  <span class="whatsapp_link">Связаться</span></a></div>
              </div>
            </div>
            <div class="logo"><img class="logo_img" src="../static/header_logo.webp" /></div>
            <div class="rectangle">
              <div class="address" @click="clickToContact">
                <nuxt-link to="/ru/kontakty">м. Балтийская, наб. Обводного канала, д.136, 4-я проходная, оф.345</nuxt-link>
              </div>
            </div>
            <div id="nav-icon1"  v-bind:class="{ open: isOpen }"  @click="this.clickToMenu">
              <span></span>
              <span></span>
              <span></span>
              <div>Меню</div>
            </div>
          </div>
          <div class="under_header"></div>
          <div v-if="isMenuOpen" class="nav"><MainMenu @clickToMenuItem="clickToMenuItem" /></div>
          <!--<div class="online_booking_btn">
            <div class="rectangle_btn">
              <div class="address">
                <a href="https://napriem.com/arcticsonicwave"
                   data-title="Онлайн бронь студийного времени"
                   data-hidemap="true"
                   class="openTimePlanMePopup">
                    Записаться онлайн
                </a>
              </div>
            </div>
          </div>-->
        </div>
      </div>
    </header>
    <script src="https://timeplan.me/js/timeplanme_integration.min.js"></script>
  </div>
</template>

<script>

    import MainMenu from '~/components/MainMenu.vue'
    import { TimelineLite } from "gsap";
    import VueScrollTo from 'vue-scrollto';

    export default {
        name: "Header",
        components: {
            MainMenu
        },
        data() {
            return {
                win_dom: null,
                isOpen: false,
                isMenuOpen: true,
                width: 0,
                options: null,
                options_2: null
            }
        },
        mounted() {
            this.win_dom = window;
            const header = this.$refs.header
            const tl = new TimelineLite()

            tl.from(header, 2, { opacity: 0, ease: Power2.easeOut, y: -150})

            this.width = document.body.clientWidth

            if(this.width <= 767) {
                this.isMenuOpen = false
            }
            this.options = {
                container: "body",
                duration: 500,
                easing: "ease",
                offset: 400,
                force: true,
                cancelable: false,
                onStart: false,
                onDone: false,
                onCancel: false,
                x: false,
                y: true
            }

            this.options_2 = {
                container: "body",
                duration: 500,
                easing: "ease",
                offset: 1200,
                force: true,
                cancelable: false,
                onStart: false,
                onDone: false,
                onCancel: false,
                x: false,
                y: true
            }

            const  { link_w_t }  = this.$refs ;

            tl.from(link_w_t , 2, { opacity: 0 })
                .to(link_w_t, 1, { duration: 5, ease: Bounce.easeOut, repeat: -1, yoyo: true, y: 5, })

        },
        methods: {
            clickToMenu() {
                this.isOpen = !this.isOpen
                this.isMenuOpen = !this.isMenuOpen
                if(this.width <= 767) {
                    VueScrollTo.scrollTo(document.body, 500, this.options)
                }
            },
            clickToMenuItem() {
                if(this.width <= 767) {
                    this.isOpen = false
                    this.isMenuOpen = false

                }
            },
            clickToContact() {
                if(this.width <= 767) {
                    VueScrollTo.scrollTo(document.body, 800, this.options_2)
                }
            }
        }
    }
</script>

<style scoped>

  .header_wrapper {
    position: fixed;
    top: 0;
    width: 100%;
    z-index: 12;
  }

  .header {
    display: flex;
    flex-direction: row;
    justify-content: center;
    background: url("../static/header_background.webp") no-repeat ;
    background-size: cover;
    height: 135px;
    margin-bottom: 2px;
    padding:0 15%;
  }

  .icon img {
    width: 30px;
    height: 30px;
    margin-right: 15px;
    margin-bottom: 5px;
  }

  .rectangle {
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin-top: -10px;
    margin-bottom: 15px;
    padding: 20px;
    background-color: #e6e6e6;
    width: 40%;
    border-radius: 10px;
    -webkit-box-shadow: 5px 1px 5px 0px rgba(50, 50, 50, 0.75);
    -moz-box-shadow:    5px 1px 5px 0px rgba(50, 50, 50, 0.75);
    box-shadow:         5px 1px 5px 0px rgba(50, 50, 50, 0.75);
  }


  .phone {
    font-family: "Roboto", sans-serif;
    color: #ff0000;
    font-size: 1rem;
    font-weight: bold;
    text-align: center;
    margin-bottom: 10px;
  }

  .messenger {
    font-family: "Roboto", sans-serif;
    color: #0d63a2;
    font-size: 1rem;
    font-weight: bold;
    text-align: center;
  }

  .whatsapp_link {
    text-transform: lowercase;
    text-decoration: underline;
    font-style: oblique;
  }

  .telegramm_link {
    text-transform: lowercase;
    text-decoration: underline;
    font-style: oblique;
  }

  .address {
    font-family: "Candara", sans-serif;
    color: #0d63a2;
    font-size: 1rem;
    font-weight: bold;
    text-align: center;
  }

  .under_header {
    background: url("../static/header_border_bottom.webp") no-repeat;
    height: 30px;
  }

  .logo {
    display: flex;
    flex-direction: row;
    justify-content: center;
    width: 100%;
  }

  .logo_img {
    width: 350px;
    height: 150px;
    border-radius: 10px;
    -webkit-box-shadow: 5px 1px 5px 0px rgba(50, 50, 50, 0.75);
    -moz-box-shadow:    5px 1px 5px 0px rgba(50, 50, 50, 0.75);
    box-shadow:         5px 1px 5px 0px rgba(50, 50, 50, 0.75);
  }

  .nav {
    display: flex;
    flex-direction: row;
    justify-content: center;
    width: 100%;
  }



  #nav-icon1 {
    display: none;
    width: 60px;
    height: 45px;
    position: relative;
    margin: 50px auto;
    -webkit-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    transform: rotate(0deg);
    -webkit-transition: .5s ease-in-out;
    -moz-transition: .5s ease-in-out;
    -o-transition: .5s ease-in-out;
    transition: .5s ease-in-out;
    cursor: pointer;
  }

  #nav-icon1 span {
    display: block;
    position: absolute;
    height: 9px;
    width: 100%;
    background: #055087;
    border-radius: 9px;
    opacity: 1;
    left: 0;
    -webkit-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    transform: rotate(0deg);
    -webkit-transition: .25s ease-in-out;
    -moz-transition: .25s ease-in-out;
    -o-transition: .25s ease-in-out;
    transition: .25s ease-in-out;
  }

  #nav-icon1 span:nth-child(1) {
    top: 0px;
  }

  #nav-icon1 span:nth-child(2) {
    top: 18px;
  }

  #nav-icon1 span:nth-child(3) {
    top: 36px;
  }

  #nav-icon1.open span:nth-child(1) {
    top: 18px;
    -webkit-transform: rotate(135deg);
    -moz-transform: rotate(135deg);
    -o-transform: rotate(135deg);
    transform: rotate(135deg);
  }

  #nav-icon1.open span:nth-child(2) {
    opacity: 0;
    left: -60px;
  }

  #nav-icon1.open span:nth-child(3) {
    top: 18px;
    -webkit-transform: rotate(-135deg);
    -moz-transform: rotate(-135deg);
    -o-transform: rotate(-135deg);
    transform: rotate(-135deg);
  }

  #nav-icon1 div {
    position: absolute;
    top: 100%;
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: center;
    color: #8dd1ec;
    text-transform: uppercase;
    margin-top: 28px;
  }



  @media (max-width: 319px) {
    #nav-icon1 {
      display: block;
      margin-top: 10px;
      margin-bottom: 10px;
    }

    #nav-icon1 div {

    }

    .header_wrapper {
      position: relative;
      top: 0;
      width: 100%;
    }

    .phone {
      font-size: 1rem;
    }

    .address {
      font-size: 1rem;
    }

    .logo_img {
      width: 150px;
      height: 70px;
    }
    .header {
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 0;
      height: 500px;
    }

    .rectangle {
      margin: 10px auto;
      width: 150px;
    }

    .rectangle_btn {
      margin-top: 0;
    }

  }

  @media (min-width: 320px) and (max-width: 577px) {
    #nav-icon1 {
      display: block;
      margin-top: 0;
    }

    #nav-icon1 div {
      position: absolute;
      margin-top: 20px;
    }

    .header_wrapper {
      position: relative;
      top: 0;
      width: 100%;
    }

    .logo_img {
      width: 270px;
      height: 100px;
    }

    .header {
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 0;
      height: 480px;
    }

    .rectangle {
      margin: 10px auto;
      width: 270px;
    }

    .rectangle_btn {
      margin-top: 0;
    }

    .icon img {
      margin-bottom: 5px;
    }
  }

  @media (min-width: 578px) and (max-width: 811px) {
    #nav-icon1 {
      display: block;
      margin-top: 3%;
    }

    .header_wrapper {
      position: relative;
      top: 0;
      width: 100%;
    }

    .header {
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 0;
      height: 520px;
    }

    .rectangle {
      margin: 10px auto;
      width: 350px;
    }

    .rectangle_btn {
      margin-top: 0;
    }

    .phone {
      font-size: 0.8rem;
    }

    .messenger {
      font-size: 0.8rem;
    }

    .icon img {
      margin-bottom: 5px;
    }
  }

  @media (min-width: 812px) and (max-width: 1179px) {
    .header {
      padding: 0 5%;
    }

    .phone {
      font-size: 0.9rem;
    }

    .messenger {
      font-size: 0.8rem;
    }

    .rectangle_btn {
      margin-top: 0;
    }

    .icon img {
      margin-right: 5px;
      margin-bottom: 5px;
    }
  }

  @media (min-width: 1180px) and (max-width: 1255px) {
    .phone {
      font-size: 1rem;
    }

    .messenger {
      font-size: 0.9rem;
    }

    .icon img {
      margin-bottom: 5px;
    }
  }

</style>
