<template>
  <div class="abt-p">
      <div class="abt-main">
        <h3>About this project</h3>
        <p>The Mastercraft Bamboo Monitor Riser is a sturdy and stylish platform that elevates your screen to a more
            comfortable viewing height. Placing your monitor at eye level has the potential to improve your posture and
            make you more comfortable while at work, helping you stay focused on the task at hand.
        </p>
        <p>Featuring artisan craftmanship, the simplicityof design creates extra desk space below your computer to allow
            notepads, pens, and USB sticks to be stored under the stand.
        </p>
        <div class="bst-cont">
            <div class="bst-in">
                <div class="bst">
                    <div id="bbs">Bamboo Stand</div>
                    <div></div>
                    <div id="pld">Pledge $25 or more</div>
                </div>
                <div id="erg">You get an ergonomic stand made of bamboo. You've helped us launch our promotional campaign, 
                    and you'll be added to a special Backer member list.
                </div>
                <div class="srw">
                    <div id="lft">101 <span>left</span></div>
                    <div></div>
                    <div><button id="slr">Select Reward</button></div>
                </div>
            </div>
        </div>
        <div class="bst-cont">
            <div class="bst-in">
                <div class="bst">
                    <div id="bbs">Black Edition Stand</div>
                    <div></div>
                    <div id="pld">Pledge $75 or more</div>
                </div>
                <div id="erg">You get a Black Special Edition computer and a personal thank you. 
                    you'll be added to our Backer member list. Shipping is included.
                </div>
                <div class="srw">
                    <div id="lft">64 <span>left</span></div>
                    <div></div>
                    <div><button id="slr">Select Reward</button></div>
                </div>
            </div>
        </div>
        <div class="bst-cont">
            <div class="bst-in">
                <div class="bst">
                    <div id="bbs">Mahogany Special Edition</div>
                    <div></div>
                    <div id="pld">Pledge $200 or more</div>
                </div>
                <div id="erg">You get two Special Mahogany stands, a Backer T-Shirt, and a personal thank you.
                    You'll be added to our Backer member list. Shipping is included
                </div>
                <div class="srw">
                    <div id="lft">0 <span>left</span></div>
                    <div></div>
                    <div><button id="slr">Out of stock</button></div>
                </div>
            </div>
        </div>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.abt-p {
    background: white;
    width: 50%;
    margin: 10px auto;
    border-radius: 5px;
}
.abt-main {
    padding-bottom: 30px;
}
h3, p {
    width: 90%;
    margin-left: auto;
    margin-right: auto;
    font-family: "Commissioner" sans-serif;
}
h3 {
    padding-top: 30px;
}
p {
    padding-top: 10px;
    line-height: 1.5em;
}
.bst-cont {
    width: 90%;
    margin: 10px auto;
    display: grid;
    grid-template-rows: auto auto auto;
    border: 1px solid hsl(0, 11%, 85%);
    border-radius: 5px;
}
.bst-in {
    width: 90%;
    margin: 20px auto;
}
.bst, .srw {
    display: grid;
    grid-template-columns: 30% 40% 30%;
    padding-top: 20px;
    padding-bottom: 20px;
    align-items: center;
}
#slr {
    width: 100%;
    height: 40px;
    border-radius: 50px;
    background: hsl(176, 72%, 28%);
    border-style: none;
    color: white;
    font-weight: bold;
}
#slr:hover {
    font-weight: 400;
    background: hsl(176, 52%, 60%);
}
#pld {
    font-weight: bold;
    color: hsl(176, 50%, 47%);
    justify-content: left;
    margin-left: 8%;
}
#bbs {
    font-size: 16px;
    font-weight: 750;
}
#erg {
    line-height: 2em;
}
#lft {
    display: flex;
    font-size: 30px;
    font-weight: bold;
    align-items: center;
}
span {
    font-weight: 200;
    font-size: 0.5em;
    margin-left: 10px;
}
@media (max-width: 900px) {
    .abt-p {
        width: 80%;
    }
    .bst, .srw {
        display: block;
        align-items: left;
        justify-content: left;
    }    
    #pld {
        margin-left: 0;
        line-height: 40px;
    }
    #lft {
        line-height: 80px;
    }
}
</style>