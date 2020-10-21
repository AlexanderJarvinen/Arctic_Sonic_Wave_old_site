<template>
  <footer  ref="footer_menu">
    <div class="menu_wrapper">
      <div class="menu_stand">
        <ul>
          <li><nuxt-link to="/ru/ozvuchivanie">Озвучивание</nuxt-link></li>
          <li><nuxt-link to="/ru/audioroliki">Звук для бизнеса</nuxt-link></li>
          <li><nuxt-link to="/ru/pravila_studii">Правила студии</nuxt-link></li>
          <li><nuxt-link to="/ru/blog">Блог</nuxt-link></li>
        </ul>
      </div>
    </div>
  </footer>
</template>

<script>
    import { TimelineLite } from "gsap";

    export default {
      name: "FooterMenu",
      mounted() {
          this.scroll();
      },
      methods: {
          scroll () {
              window.onscroll = () => {
                  let bottomOfWindow = document.documentElement.scrollTop + window.innerHeight === document.documentElement.offsetHeight;

                  const  footer_menu  = this.$refs.footer_menu ;
                  const tl = new TimelineLite();

                  if (bottomOfWindow) {
                      tl.to(footer_menu , 2, { ease: Power2.easeOut, y: -59})
                  }

                  if(!bottomOfWindow) {
                      tl.to(footer_menu , 2, { ease: Power2.easeOut, y: 1})
                  }
              };
          },
      }
    }
</script>

<style scoped>
  footer {
    display: flex;
    flex-direction: row;
    justify-content: center;
    position: fixed;
    bottom: 40px;
    width: 100%;
    z-index: 12;
  }

  .menu_wrapper {
    /*padding-bottom: 40px;*/
    background-color: #000000;
    border: 1px solid #ffffff;
  }

  .menu_stand {
    font-family: 'Candara', sans-serif;
    text-transform: uppercase;
    font-weight: 300;
    font-size: 1rem;
    letter-spacing: 5px;
  }

  ul {
    list-style: none;
    margin: 10px 0;
  }

  li {
    padding: 0 20px;
    display: inline;
    border-right: 2px solid #f2f2f2;
    color: #f2f2f2 !important;
    cursor: pointer;
  }

  li:hover {
    color: #ffffff !important;
    font-weight: bold;
    text-shadow: -3px -1px 9px rgba(255, 255, 255, 1);
  }

  li:last-child {
    border-right: none;
  }

  a {
    color: #f2f2f2 !important;
  }

  @media (max-width: 319px) {
    .menu_stand {
      width: 100%;
    }

    li {
      margin-left: 20px;
      display: block;
      border: none;
      padding: 20px 0;
    }
  }

  @media (min-width: 320px) and (max-width: 577px) {
    footer {
      display: block;
    }

    .menu_stand {
      width: 100%;
    }

    ul {
      padding: 20px 0;
    }

    li {
      padding: 15px 0;
      margin-left: 20px;
      display: block;
      border: none;
    }
  }


  @media (min-width: 578px) and (max-width: 767px) {
    .menu_stand {
      font-size: 0.8rem ;
      letter-spacing: 1px;
    }

    li {
      padding: 0 5px;
    }
  }

  @media (min-width: 768px) and (max-width: 1060px) {
    footer {
     display: block;
    }

    .menu_wrapper {
      display: flex;
      flex-direction: row;
      justify-content: center;
      width: 100%;
    }

    .menu_stand {
      font-size: 0.8rem;
      letter-spacing: 3px;
    }

    li {
      padding: 0 5px;
    }
  }


</style>
