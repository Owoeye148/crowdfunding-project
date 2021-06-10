<template>
    
    <div v-if="close_" class="b_modal">
        <div id="btpj">
            <div class="btp-inner">
                <label @click="close_b_modal" for="close" class="closebtn">
                    <i id="close" class="fa fa-close"></i>
                </label>
                <h3>Back this project</h3>
                <p id="want">Want to support us in bringing MasterCraft Bamboo Monitor Riser out in the world?</p>
                <form action="">
                    <div class="hfg">
                        <div class="hfg-inner">
                            <input type="radio" id="pwnr" name="pledge">
                            <label for="pwnr">
                                <h4 id="plnr">Pledge with no reward</h4>
                                <p class="ben" id="pwnr-ben">
                                    Choose to support us without a reward if you simply believe in our project. 
                                    As a backer, you will be signed up to receive product updates via email.
                                </p>
                            </label>
                        </div>
                    </div>
                    <div class="hfg">
                        <div class="hfg-inner">
                            <input type="radio" id="bambo-st" name="pledge" @click="toggleBS_pledge()">
                            <label for="bambo-st">
                                <div class="plgp"> 
                                    <div id="bsp">
                                        <h4 class="prj">Bamboo Stand</h4>
                                        <div id="spc"></div>
                                        <p class="pla">Pledge $25 or more</p>
                                    </div>
                                    <div class="lft">101<small>left</small></div>
                                </div>
                                <p class="ben">
                                    You get an ergonomic stand made of bamboo. You've helped us launch our promotional campaign, 
                                    and you'll be added to a special Backer member list.
                                </p>
                            </label>
                            <div class="lft-m">101<small>left</small></div>
                            <div v-if="!bs_pledgeShow" class="eyp">
                                <div>
                                    <p>Enter your pledge</p>
                                </div>
                                <div class="inp-no">
                                    <form @submit="open_thanks_modal()">
                                        <div class="ent">
                                            $<input id="in-a" type="number" required min="25">
                                        </div>
                                        <div class="cont">
                                            <button id="submit_pledge" type="submit">Continue</button>
                                        </div>
                                    </form>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="hfg">
                        <div class="hfg-inner">
                        <input type="radio" id="black-es" name="pledge" @click="toggleBS_pledge()">
                            <label for="black-es">
                                <div class="plgp"> 
                                    <div id="bsp">
                                        <h4 class="prj">Black Edition Stand</h4>
                                        <div id="spc"></div>
                                        <p class="pla">Pledge $75 or more</p>
                                    </div>
                                    <div class="lft">64<small>left</small></div>
                                </div>
                                <p class="ben">
                                    You get a Black Special Edition computer and a personal thank you. you'll be added to our Backer member list. Shipping is included.
                                </p>
                            </label>
                            <div class="lft-m">64<small>left</small></div>
                            <div v-if="!bs_pledgeHide" class="eyp">
                                <div>
                                    <p>Enter your pledge</p>
                                </div>
                                <div class="inp-no">
                                    <form v-on:submit="open_thanks_modal()">
                                        <div class="ent">
                                            $<input id="in-a" type="number" required min="75">
                                        </div>
                                        <div class="cont">
                                            <button id="submit_pledge" type="submit">Continue</button>
                                        </div>
                                    </form>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="hfg">
                        <div class="hfg-inner">
                            <input type="radio" id="mah-se" name="pledge">
                            <label for="mah-se">
                                <div class="plgp"> 
                                    <div id="bsp">
                                        <h4 class="prj" id="maho">Mahogany Special Edition</h4>
                                        <div id="spc"></div>
                                        <p class="pla">Pledge $200 or more</p>
                                    </div>
                                    <div class="lft">0<small>left</small></div>
                                </div>
                                <p class="ben">
                                    You get an ergonomic stand made of bamboo. You've helped us launch our
                                    promotional campaign, and you'll be added to a special Backer member list.
                                </p>
                            </label>
                            <div class="lft-m">0<small>left</small></div>
                        </div>
                    </div>
                    
                    <label for="mah-se"></label>
                </form>
            </div>
        </div>
    </div>
    <div v-if="open_t_modal">
        <ThanksModal />
    </div>
</template>

<script>
import ThanksModal from '../components/ThanksModal.vue'
export default {
    components: {
        ThanksModal
    },
    data() {
        return {
            close_: true,
            open_t_modal: false,
            bs_pledge: false,
            bs_pledgeShow: true,
            bs_pledgeHide: false

        }
    },
    methods: {
        close_b_modal() {
            this.close_ = !this.close_
        },
        open_thanks_modal() {
            this.open_t_modal = true

        },
        toggleBS_pledge() {
            this.bs_pledgeShow = !this.bs_pledgeShow
            this.bs_pledgeHide = !this.bs_pledgeHide
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
    padding-top: 50px;
    padding-bottom: 50px;
    background: rgba(0, 0, 0, 0.5);
    z-index: 2;
}
#btpj {
    width: 50%;
    background: white;
    border-radius: 8px;
    margin-top: 50px;
    margin-bottom: 50px;
    max-height: 100%;
    overflow-y: scroll;
}
.btp-inner {
    width: 90%;
    margin: 20px auto;
}
.hfg {
    display: flex;
    flex-direction: row;
    border: 1px solid rgb(103, 100, 100);
    border-radius: 5px;
    align-items: center;
    justify-content: center;
    margin: 15px auto;
}
.hfg-inner {
    margin-top: 15px;
    margin-bottom: 5px;
    margin-left: 20px;
    margin-right: 20px;
    align-items: flex-start;
}
h4 {
    line-height: 0px;
    margin: 0;
    padding: 0;
    white-space: nowrap;
    cursor: pointer;
}
p {
    font-size: 12px;
}
p#want {
    line-height: 25px;
}
h4, .ben {
    margin-left: 40px;
}
h4.prj:hover {
    color: hsl(176, 50%, 47%);
}
.ben {
    text-align: justify;
    line-height: 25px;
    margin-top: 2px;
}
#pwnr-ben {
    margin-top: 12px;
}
.plgp {
    display: grid;
    grid-template-columns: 85% 15%;
    align-items: center;
    margin-top: -19px;
}
#bsp {
    display: flex;
    flex-direction: row;
    align-items: center;
    height: 10px;
    padding: 0;
}
#plnr {
    margin-top: -10px;
}
#spc {
    width: 20px;
}
.lft {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    font-size: 20px;
    font-weight: bold;
}
.lft-m {
    display: none;
}
label {
    margin: 0;
    padding: 0;
}
.closebtn {
    display: flex;
    font-size: 15px;
    margin-left: 100%;
    margin-top: 0%;
}
small {
    margin-left: 5px;
    font-weight: 200;
    font-size: 11px;
}
.pla {
    color: hsl(176, 50%, 47%);
    white-space: nowrap;
}
@media (max-width: 900px) {
    .plgp {
        display: flex;
        flex-direction: row;
        justify-items: flex-start;
    }
    #btpj {
        overflow-y: scroll;
        width: 80%;
    }
    #plnr {
        margin-left: 40px;
    }
    #bsp {
        display: grid;
        grid-template-rows: repeat(2 1fr);
        margin-left: 40px;
    }
    h4 {
        margin-left: 0px;
        white-space: nowrap;
    }
    #spc {
        width: none;
    }
    .pla {
        margin-left: 0;
    }
    .btp-inner {
        height: auto;
    }
    .ben {
        margin-top: 15px;
        margin-left: 0;
    }
    .lft {
        display: none;
    }
    .lft-m {
        display: flex;
        align-items: center;
        font-size: 20px;
        font-weight: bold;
    }
    div.eyp {
        display: flex;
        flex-direction: column;
    }
    div.cont {
        width: 80%;
    }
    div.inp-no {
        display: grid;
        justify-items: center;
        grid-template-columns: 50% 50%;
        width: 100%;
    }
}
.eyp {
    display: grid;
    grid-template-columns: 50% 50%;
    align-items: center;
    height: 70px;
    border-top: 1px solid rgb(198, 190, 190);
    padding-left: 1.2em;
    padding-right: 1.2em;
    padding-top: 0.5em;
    padding-bottom: 0.5;
    margin: 15px -1.3em;
}
.inp-no {
    display: grid;
    grid-template-columns: 50% 50%;
}
#in-a {
    width: 30px;
    border-style: none;
}
.ent {
    display: flex;
    border: 1px solid hsl(176, 50%, 47%);
    width: 80%;
    height: 28px;
    border-radius: 50px;
    align-items: center;
    justify-content: center;
}
.cont {
    display: flex;
    align-items: center;
    justify-content: center;
    background: hsl(176, 72%, 28%);
    border-radius: 50px;
    width: 80%;
}
.cont button {
    border-style: none;
    background: none;
    color: white;
}
</style>