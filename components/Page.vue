<template>
  <div>
    <div class="page-content" ref="page">
      <!--<div class="vert" ref="btn" ><span>Оставить заявку</span></div>-->
      <slot></slot>
    </div>
  </div>
</template>

<script>
  import { TimelineLite } from "gsap";

  export default {
    name: "Page",
    /*mounted() {
      const  btn  = this.$refs.btn;
      const tl = new TimelineLite();

      tl.from(btn , 2, { opacity: 0, delay:2})
    }*/
  }
</script>

<style scoped>

  .page-content {
    background-color: rgba(225, 225, 225, 0.7);
    margin: 15% 20% 5%;
    padding: 2%;
    border: 2px solid rgba(0, 113, 188, 0.6);
    border-radius: 15px  15px 15px 15px;
    min-height: 500px;
    max-height: 100%;
    overflow: auto;
    z-index: 2000;
  }

  .page-content h1 {
    color: #000000;
    font-family: "Candara", sans-serif;
    font-weight: bolder;
    text-align: center;
  }

  .page-content h2 {
    color: #000000;
    font-family: "Candara", sans-serif;
    font-weight: bold;
    text-align: center;
  }

  .page-content h4 {
    color: #000000;
    font-family: "Candara", sans-serif;
    font-weight: bold;
    text-align: center;
    margin-top: 10vh;
    margin-bottom: 5vh;
  }

  .page-content h5 {
    color: #000000;
    font-family: "Candara", sans-serif;
    font-weight: bold;
    text-align: center;
  }

  .page-content img {
    min-width: 100%;
    max-width: 100%;
    height: auto;
  }

  .page-content ul li {
      list-style-type: square;
    }

  .vert{
    position: fixed;
    left: calc(20% - 164px);
    top:calc(45% - 20px);
    transform: rotate(-90deg);
  }

  .vert span {
    -webkit-transform: rotate(90deg);
    transform: rotate(90deg);
    text-align: left;
    padding: 10px 60px;
    border: 2px solid #cccccc;
    background-color: #ffffff;
    border-radius: 200px 0 0 0;
    text-transform: uppercase;
    font-weight: bold;
  }

  .vert span:hover {
    cursor: pointer;
    background-color: #000000;
    color: #f2f2f2;
  }



  @media (max-width: 319px) {
    .page-content {
      margin: 3vh 5% 5%;
      border: 2px solid rgba(0, 113, 188, 0.6);
      padding: 5%;
    }

  }

  @media (min-width: 320px) and (max-width: 577px) {
    .page-content {
      margin: 3vh 5% 5%;
      border: 2px solid rgba(0, 113, 188, 0.6);
      padding: 5%;
    }


  }

  @media (min-width: 578px) and (max-width: 767px) {
    .page-content {
      margin: 3vh 10% 5%;
      border: 2px solid rgba(0, 113, 188, 0.6);
      padding: 5%;
    }


  }

  @media (min-width: 768px) and (max-width: 1028px) {
    .page-content {
      margin: 30% 10% 0;
      border: 2px solid rgba(0, 113, 188, 0.6);
      padding: 5%;
    }



  }

  @media (min-width: 1029px) and (max-width: 1280px) {
    .page-content {
      margin: 20% 5% 5%;
      padding: 5%;
    }



  }

  p {
    color: #000000;
  }
</style>
