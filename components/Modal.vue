<template>
    <div class="overlay">
      <div class="modal_wrapper">
        <div class="modal">
          <div class="modal_header"><div class="modal_cross" @click="closeModal">✖</div></div>

          <slot></slot>
        </div>
      </div>
    </div>
</template>

<script>
    export default {
        name: "Modal",
        methods: {
          closeModal() {
            this.$emit('closeModal');
          }
        }
    }
</script>

<style scoped>
 .overlay {
   position: fixed;
   top: 0;
   left: 0;
   background-color: rgba(0, 0, 0, 0.5);
   z-index: 1000;
   width: 100vw;
   height: 100vh;
   overflow: hidden;
 }

 .modal_wrapper {
   width: 100vw;
 }

  .modal {
    margin-left: 15%;
    background-color: rgba(225, 225, 225);
    padding: 2%;
    border: 2px solid rgba(0, 113, 188, 0.6);
    border-radius: 15px;
    overflow: auto;
    z-index: 1001;
    display: block;
    width: 70%;
  }

  .modal_header {
    height: 5%;
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    z-index: 1150;
  }

  .modal_cross {
    position: fixed;
    top: 2%;
    right: 18%;
    font-size: 1.5em;
    color: rgba(0, 113, 188, 0.6);
    cursor: pointer;
  }

</style>
