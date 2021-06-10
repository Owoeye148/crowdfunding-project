<template>
  <div class="modal" v-if="!close">
      <div class="modal-container">
        <div class="modal_content">
            <div class="img-cont">
                <img src="~@/assets/img/icon-check.svg" alt="check">
            </div>
            <h5>Thanks For your support!</h5>
            <p>Your pledge brings us one step closer to sharing MasterCraft Bamboo Monitor Riser worldwide. You will get an email once our campaign is completed</p>
            <div class="btn-cont">
                <button type="button" @click="close_t_modal">Got it!</button>
            </div>
        </div>
      </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            close:  true
        }
    },
    methods: {
        close_t_modal() {
        this.close = !this.close
        }
    }

}
</script>

<style scoped>
.modal {
    display: flex;
    align-items: center;
    justify-content: center;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.6);
    z-index: 4;
}
.modal-container {
    display: flex;
    width: 29%;
    background: white;
    border-radius: 8px;
}
h5, p {
    text-align: center;
}
p {
    font-size: 12px;
    margin: 5px 30px;
    line-height: 25px;
    text-align: center;
}
.img-cont {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
}

img {
  width: 2.5em;
  margin-top: 20px;
}
.btn-cont {
    width: 100%;
    justify-content: center;
    display: flex;
}
button {
    width: 20%;
    height: 30px;
    border-radius: 50px;
    margin: 20px auto;
    border-style: none;
    background: hsl(176, 72%, 28%);
    color: white;
}
@media (max-width: 900px) {
    .modal-container {
        width: 50%;
        height: 60vh;
    }
}
</style>