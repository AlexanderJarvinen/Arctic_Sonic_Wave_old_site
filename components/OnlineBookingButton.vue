<template>
  <div>
    <div>
      <div class="online_booking_wrapper" ref="booking_button">
        <div class="booking_button" @click="booking"><a href="#" >Записаться онлайн</a></div>
      </div>
      <modal v-if="modalOpen" @closeModal="closeModal">
        <iframe class="booking_frame" src="https://napriem.com/arcticsonicwave?min=1&hideall=1" width="1000" height="760" frameborder="0"></iframe>
      </modal>
    </div>
  </div>
</template>

<script>
    import Modal from "./Modal";
    import { TimelineLite } from "gsap";

    export default {
        name: "OnlineBookingButton",
        components: {
            Modal
        },
        data() {
            return {
                modalOpen: false
            }
        },
        mounted() {
            document.addEventListener("DOMContentLoaded", this.startAnimation());
        },
        methods: {
            booking() {
               if (document.body.clientWidth > 1540) {
                   this.modalOpen = true
               } else {
                   window.open("https://napriem.com/arcticsonicwave")
               }
            },
            closeModal() {
                this.modalOpen = false
            },
            startAnimation() {
                const  booking_button  = this.$refs.booking_button ;
                const tl = new TimelineLite();

                tl.from(booking_button , 2, { opacity: 0, ease: Power2.easeOut, x: 200})
                    .to(booking_button, 1, { duration: 2.5, ease: Circ.easeOut, repeat: -1, yoyo: true, y: -20, })
            }
        }
    }
</script>

<style scoped>
  .online_booking_wrapper {
    position: fixed;
    right: 15%;
    bottom: 17%;
    z-index: 1000;
  }

  .booking_button {
    display: flex;
    flex-direction: column;
    justify-content: center;
    width: 130px;
    height: 130px;
    border-radius: 70px;
    background-color: #005da2;
    border: 2px solid #ffffff;
    color:#ffffff;
    padding: 20px;
    cursor: pointer;

  }

  .booking_button:hover {
    color: #85aac5;
    border: 2px solid #85aac5;
  }

  .booking_button a {
    color:#ffffff;
    text-align: center;
  }



  .booking_frame {
    margin-top: 3%;

  }

  @media (max-width: 319px) {
    .online_booking_wrapper {
      right: 5%;
      bottom: 30%;
    }
    .booking_button {
      width: 100px;
      height: 100px;
      border-radius: 70px;
      padding: 10px;
      font-size: 0.9rem;

    }


  }

  @media (min-width: 320px) and (max-width: 577px) {
    .online_booking_wrapper {
      right: 5%;
      bottom: 30%;
    }
    .booking_button {
      width: 100px;
      height: 100px;
      border-radius: 70px;
      padding: 10px;
      font-size: 0.9rem;

    }


  }

  @media (min-width: 578px) and (max-width: 767px) {
    .online_booking_wrapper {
      right: 5%;
      bottom: 20%;
    }
    .booking_button {
      width: 100px;
      height: 100px;
      border-radius: 70px;
      padding: 10px;
      font-size: 0.9rem;

    }
  }

  @media (min-width: 768px) and (max-width: 1060px) {
    .online_booking_wrapper {
      right: 5%;
      bottom: 20%;
    }
    .booking_button {
      width: 100px;
      height: 100px;
      border-radius: 70px;
      padding: 10px;
      font-size: 0.9rem;

    }
  }
</style>
