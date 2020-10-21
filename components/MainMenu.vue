<template>
  <div class="menu_stand">
    <ul v-if="width > 811">
      <li  @click="$emit('clickToMenuItem')" ><nuxt-link to="/ru/glavnaya">Главная</nuxt-link></li>
      <li  @click="$emit('clickToMenuItem')" ><nuxt-link to="/ru/oborudovanie">Оборудование</nuxt-link></li>
      <li  @click="$emit('clickToMenuItem')" ><nuxt-link to="/ru/uslugi">Услуги</nuxt-link></li>
      <li  @click="$emit('clickToMenuItem')" ><nuxt-link to="/ru/portfolio">Портфолио</nuxt-link></li>
      <li  @click="$emit('clickToMenuItem')" ><nuxt-link to="/ru/kontakty">Контакты</nuxt-link></li>
    </ul>
    <ul v-if="width < 811">
      <li  @click="$emit('clickToMenuItem')" ><nuxt-link to="/ru/glavnaya">Главная</nuxt-link></li>
      <li  @click="$emit('clickToMenuItem')" ><nuxt-link to="/ru/oborudovanie">Оборудование</nuxt-link></li>
      <li  @click="$emit('clickToMenuItem')" ><nuxt-link to="/ru/uslugi">Услуги</nuxt-link></li>
      <li  @click="$emit('clickToMenuItem')" ><nuxt-link to="/ru/portfolio">Портфолио</nuxt-link></li>

      <li  @click="$emit('clickToMenuItem')" ><nuxt-link to="/ru/ozvuchivanie">Озвучивание</nuxt-link></li>
      <li  @click="$emit('clickToMenuItem')" ><nuxt-link to="/ru/audioroliki">Звук для бизнеса</nuxt-link></li>
      <li  @click="$emit('clickToMenuItem')" ><nuxt-link to="/ru/pravila_studii">Правила студии</nuxt-link></li>
      <li  @click="$emit('clickToMenuItem')" ><nuxt-link to="/ru/blog">Блог</nuxt-link></li>
    </ul>
  </div>
</template>

<script>
    export default {
      name: "MainMenu",
      data () {
        return {
          width: 0
        }
      },
      mounted() {
          this.width = document.body.clientWidth
      }
    }
</script>

<style scoped>

  .menu_stand {
    font-family: 'Candara', sans-serif;
    text-transform: uppercase;
    font-weight: 300;
    font-size: 1rem;
    background-color: #000000;
    letter-spacing: 5px;
    border: 1px solid #ffffff;
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

  @media (min-width: 578px) and (max-width: 811px) {
    .menu_stand {
      width: 100%;
      font-size: 1rem ;
      letter-spacing: 1px;
    }

    li {
      padding: 15px 0;
      margin-left: 20px;
      display: block;
      border: none;
    }
  }


  @media (min-width: 812px) and (max-width: 1028px) {
    .menu_stand {
      font-size: 1rem ;
      letter-spacing: 3px;
    }

    li {
      padding: 0 10px;
    }
  }


</style>
