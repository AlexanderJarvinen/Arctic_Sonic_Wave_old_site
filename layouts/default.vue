<template>
  <div>
    <Header />
    <nuxt class="nuxt" />
    <Footer />
    <Background />
    <FooterMenu v-if="width > 811" />
    <online-booking-button/>
    <script  src="//code.jivosite.com/widget.js" data-jv-id="5Fz9R2j0fe" async></script>
  </div>
</template>
<!--<script v-if = "this.$route.path != '/'" src="//code.jivosite.com/widget.js" data-jv-id="5Fz9R2j0fe" async></script>-->
<!--<script type="text/javascript">!function(){var t=document.createElement("script");t.type="text/javascript",t.async=!0,t.src="https://vk.com/js/api/openapi.js?162",t.onload=function(){VK.Retargeting.Init("VK-RTRG-412233-6RIM7"),VK.Retargeting.Hit()},document.head.appendChild(t)}();</script><noscript><img src="https://vk.com/rtrg?p=VK-RTRG-412233-6RIM7" style="position:fixed; left:-999px;" alt=""/></noscript>-->
<script>

  import Background from "../components/Background";
  import Header from "../components/Header";
  import Footer from "../components/Footer";
  import FooterMenu from "../components/FooterMenu";
  import OnlineBookingButton from "../components/OnlineBookingButton";

  export default {
    components: {
      Background,
      Header,
      Footer,
      FooterMenu,
      OnlineBookingButton
    },
      data () {
        return {
            width: 0,
        }
      },
    mounted() {
      this.width = document.body.clientWidth


      let recaptchaScript = document.createElement('script')
      recaptchaScript.setAttribute('src', 'https://www.googletagmanager.com/gtag/js?id=UA-149067175-1')
      document.head.appendChild(recaptchaScript)

        /*let jivoScript = document.createElement('script')
        jivoScript.setAttribute('src', '//code.jivosite.com/widget.js')
        document.head.appendChild(jivoScript)*/


        window.dataLayer = window.dataLayer || [];
        function gtag(){dataLayer.push(arguments);}
        gtag('js', new Date());

        gtag('config', 'UA-149067175-1');



      (function(m,e,t,r,i,k,a){m[i]=m[i]||function(){(m[i].a=m[i].a||[]).push(arguments)};
              m[i].l=1*new Date();k=e.createElement(t),a=e.getElementsByTagName(t)[0],k.async=1,k.src=r,a.parentNode.insertBefore(k,a)})
            (window, document, "script", "https://mc.yandex.ru/metrika/tag.js", "ym");

            ym(55149115, "init", {
              clickmap:true,
              trackLinks:true,
              accurateTrackBounce:true,
              webvisor:true
            });

    }
  }
</script>
<style>
  html {
    font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
    font-size: 16px;
    word-spacing: 1px;
    -ms-text-size-adjust: 100%;
    -webkit-text-size-adjust: 100%;
    -moz-osx-font-smoothing: grayscale;
    -webkit-font-smoothing: antialiased;
    box-sizing: border-box;
    color: #e6f2ff;
  }

  body {
    overflow-x: hidden;
    height: 100%;
  }

  *, *:before, *:after {
    box-sizing: border-box;
    margin: 0;
  }

  a {
    text-decoration: none !important;
  }


  ul {
    padding: 0 !important;
  }



  .nuxt {
    margin-top: 18rem;
    min-height: 100%;
  }



  @media (max-width: 319px) {


    .nuxt {
      margin-top: 2vh;
    }

  }

  @media (min-width: 320px) and (max-width: 577px) {


    .nuxt {
      margin-top: 2vh;
    }

  }

  @media (min-width: 578px) and (max-width: 767px) {

    .nuxt {
      margin-top: 2vh;
    }
  }

  @media (min-width: 768px) and (max-width: 1028px) {
    .nuxt {
      margin-top: 7vh;
    }
  }
</style>


