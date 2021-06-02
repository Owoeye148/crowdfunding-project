<template>
  <div v-if="close" class="b_modal">
      <div id="btp">
          <div class="btp-inner">
            <label @click="close_b_modal" for="close" class="closebtn">
                <i id="close" class="fa fa-close"></i>
            </label>
            <h3>Back this project</h3>
            <p>Want to support us in bringing MasterCraft Bamboo Monitor Riser out in the world?</p>
            <div class="nrp">
                <input type="checkbox" id="check">
                <div class="pwr">
                    <div class="pwnw" for="check">
                        <h4>Pledge with no reward</h4>
                        <p class="bnft">Choose to support us without a reward if you simply believe in our project. As a backer, you will be signed up to receive product updates via email.
                        </p>
                    </div>
                </div>
            </div>
            <div class="nrp">
                <input type="checkbox" id="check">
                <div class="pwr">
                    <div class="pwnw" for="check">
                        <div class="prdt">
                            <div class="bes-plg">
                                <h4>Bamboo Stand</h4>
                                <div class="spc"></div>
                                <div class="plg"><p class="plgp">Pledge $25 or more</p></div>
                            </div>
                            <div class="lft">101 <small>left</small></div>
                        </div>
                        <p class="bnft">You get an ergonomic stand made of bamboo. You've helped us launch our promotional campaign, and you'll be added to a special Backer member list.
                        </p>
                    </div>
                </div>
            </div>
            <div class="nrp">
                <input type="checkbox" id="check">
                <div class="pwr">
                    <div class="pwnw" for="check">
                        <div class="prdt">
                            <div class="bes-plg">
                                <h4 id="blest">Black Edition Stand</h4>
                                <div class="spc"></div>
                                <div class="plg"><p class="plgp">Pledge $75 or more</p></div>
                            </div>
                            <div class="lft">64 <small>left</small></div>
                        </div>
                        <p class="bnft">You get a Black Special Edition computer and a personal thank you. you'll be added to our Backer member list. Shipping is included.
                        </p>
                    </div>
                </div>
            </div>
            <div class="nrp">
                <input type="checkbox" id="check">
                <div class="pwr">
                    <div class="pwnw" for="check">
                        <div class="prdt">
                            <div class="bes-plg">
                                <h4>Mahogany Special Edition</h4>
                                <div class="spc"></div>
                                <div class="plg"><p class="plgp">Pledge $200 or more</p></div>
                            </div>
                            <div class="lft">0<small>left</small></div>
                        </div>
                        <p class="bnft">
                            You get an ergonomic stand made of bamboo. You've helped us launch our
                            promotional campaign, and you'll be added to a special Backer member list.
                        </p>
                    </div>
                </div>
            </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    beforeDestroy(){
        this.$nuxt.$off('invest-info')
    },
    data() {
        return {
            locks: false,
            close: true,
        }
    },
    methods: {
        closeSide(){
            this.locks = !this.locks
        },
        close_b_modal() {
            this.close = !this.close
        }

    }
}
</script>

<style scoped>

.b_modal {
    display: flex;
    align-items: center;
    justify-content: center;
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background: rgba(0, 0, 0, 0.5);
}
#btp {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 60%;
    margin-top: 50px;
    margin-bottom: 50px;
    margin-left: 20%;
    margin-right: 24%;
    background: white;
    height: auto;
    border-radius: 8px;
}
.btp-inner {
    width: 90%;
    height: auto;
}
.nrp {
    display: grid;
    grid-template-columns: 10% 90%;
    border: 1px solid black;
    margin: 10px auto;
}
@media (max-width: 900px) {
    .btp {
        position: absolute;
    }
    .nrp {
        height: 250px;
    }
    .prdt {
        display: flex;
        flex-direction: column;
        justify-items: left;
        text-align: left;
    }
    .bes-plg {
        display: flex;
        justify-items: left;
        flex-direction: column;
        text-align: left;
    }
    .lft {
        position: absolute;
        float: bottom;
        margin-top: 41%;
    }
    h4 {
        line-height: 1px;
        margin-left: -25px;
    }
    #blest {
        margin-left: 10px;
    }
    .plg {
        margin-top: -20px;
    }
}
#close {
    display: flex;
}
.closebtn {
    line-height: 40px;
    display: flex;
    font-size: 15px;
    margin-left: 99%;
    margin-top: 4%;
}
#check {
    margin-top: 45%;
    margin-left: 30%;
}
.prdt {
    display: grid;
    grid-template-columns: 85% 15%;
    align-items: center;
}
.bes-plg {
    display: flex;
    align-items: center;
}
.bnft {
    width: 97%;
    font-size: 14px;
    line-height: 1.5em;
    margin-top: -5px;
    margin-left: 0;
    margin-right: 0px;
    text-align: justify;
}
.spc {
    width: 20px;
}
.lft {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    font-weight: bold;
    font-size: 20px;
    margin-right: 15px;
}
h4 {
    white-space: nowrap;
}
small {
    margin-left: 4px;
    font-weight: 300;
}
.plg {
    color: hsl(176, 69%, 42%);
    font-weight: 600;
}

</style>