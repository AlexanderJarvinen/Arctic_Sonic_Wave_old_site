<template>
    <div>
      <footer ref="footer" class="footer_wrapper">
        <div>
          <div class="foot_mountains"></div>
          <div class="foot_content">
            <div class="copyright_wrapper">
              <div class="copyright">
                <div><h3>© Arctic Sonic Wave, 2019</h3></div>
                <div><a href="mailto:admin@arcticsonicwave.com?subject=Вопрос с сайта Arctic Sonic Wave&body=Здравствуйте, у меня есть вопрос. Необходима консультация."><h3>E-mail: admin@arcticsonicwave.com</h3></a></div>
              </div>
            </div>
          </div>
        </div>
      </footer>
    </div>
</template>

<script>
  import { TimelineLite } from "gsap";

    export default {
        name: "Footer",
      mounted() {
        const footer = this.$refs.footer
        const tl = new TimelineLite()

        tl.from(footer, 2, { opacity: 0, ease: Power2.easeOut, y: 150})

      }
    }
</script>

<style scoped>

    footer {
      height: 350px;
      margin-top: -140px;
    }


   .foot_content {
     background: url("../static/footer_background.webp") no-repeat;
     height: 100px;
     z-index: 1;
   }

   .foot_mountains {

     background: url("../static/mountains.png");
     height: 250px;
     z-index: -1000;
     opacity: 0.5;
   }

   .copyright_wrapper {
     display: flex;
     flex-direction: row;
     justify-content: center;
     width: 100%;
   }

   .copyright {
     display: flex;
     flex-direction: row;
     justify-content: center;
     color: #f2f2f2;
     font-family: 'Bahnschrift', sans-serif;
     margin-left: 20px;
     padding-top: 30px;
   }

  .copyright div h3 {
     text-align: center;
     font-size: 1rem;
     margin-left: 40px;
  }

    .copyright div a {
      color: #ffffff;
      text-decoration: underline !important;
    }

    .copyright div a:hover {
      color: #ccc;
    }

  @media (max-width: 319px) {
    .foot_mountains {
      background: url("../static/mountains_small.png") no-repeat;
    }

    footer {
      height: 500px;
      margin-top: -40px;
    }

    .foot_content {
      background: url("../static/footer_background.webp") no-repeat;
      background-size: cover;
      height: 250px;
    }

    .copyright {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      padding-top: 20px;
    }

    .copyright_wrapper {
      display: flex;
      flex-direction: row;
      justify-content: flex-start;
      width: 100%;
    }

    .copyright div h3[data-v-0d2d6594] {
      text-align: left;
      font-size: 1rem;
      margin: 30px 0;
    }

  }

  @media (min-width: 320px) and (max-width: 577px) {
    .foot_mountains {
      background: url("../static/mountains_medium.png") no-repeat;
    }

    footer {
      height: 500px;
      margin-top: -40px;
    }

    .foot_content {
      background: url("../static/footer_background.webp") no-repeat;
      background-size: cover;
      height: 250px;
    }

    .copyright {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .copyright_wrapper {
      display: flex;
      flex-direction: row;
      justify-content: flex-start;
      width: 100%;
    }

    .copyright div h3[data-v-0d2d6594] {
      text-align: left;
      font-size: 1rem;
      margin: 30px 0;
    }
  }

  @media (min-width: 578px) and (max-width: 767px) {
    .foot_mountains {
      background: url("../static/mountains_medium.png") no-repeat;
    }

    footer {
      height: 350px;
      margin-top: -40px;
    }
  }

    @media (min-width: 768px) and (max-width: 1024px) {
      footer {
        height: 350px;
        margin-top: -40px;
      }
    }



</style>
