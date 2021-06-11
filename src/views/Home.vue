<template>
  <div class="home">
    <BackProject  v-if="open" />
    <div id="nav">
      <nav>
        <input type="checkbox" id="toggle" />
        <label for="toggle" class="togglebtn">
          <i id="bars" class="fas fa-bars"></i>
          <i id="close" class="fa fa-close"></i>
        </label>
        <label class="logo">crowdfund</label>
        <ul class="menu">
          <li class="nav-menu"><nuxt-link>About</nuxt-link></li>
          <li class="nav-menu"><nuxt-link>Discover</nuxt-link></li>
          <li class="nav-menu"><nuxt-link>Get Started</nuxt-link></li>
        </ul>
      </nav>
    </div>
    <div class="master-craft-cont">
      <div class="master-craft">
        <img
          id="mc"
          src="~@/assets/img/logo-mastercraft.svg"
          alt="mastercraft"
        />
        <div class="mbh">
          <h4>MasterCraft Bamboo Monitor Riser</h4>
          <p>
            A beautiful & handcrafted monitor stand to reduce neck and eye
            strain
          </p>
        </div>
        <div class="back">
          <div id="btp">
            <button type="button" @click="open_b_modal"  id="btp-button">Back this project</button>
          </div>
          <div></div>
          <div class="book">
            <img
              id="book-m"
              src="~@/assets/img/icon-bookmark.svg"
              alt="bookmark"
            />
            <div></div>
            <button><span>Bookmark</span></button>
          </div>
        </div>
      </div>
      <div class="main-backed">
        <div id="fig-backed">
          <div class="fig-backed-item">
            <div class="fig">${{ percent_baked.toLocaleString("en") }}</div>
            <div class="fiw">of $100,000 backed</div>
          </div>
          <div class="fig-backed-item">
            <div class="fig">{{ total_backers.toLocaleString("en") }}</div>
            <div class="fiw">total backers</div>
          </div>
          <div class="fig-backed-item">
            <div class="fig">{{ days_left }}</div>
            <div class="fiw">days left</div>
          </div>
        </div>
        <div id="carousel">
          <progress
            :value="percent_baked"
            :min="min_backable"
            :max="max_backable"
          />
        </div>
      </div>
      <AboutProject />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import AboutProject from "../components/AboutProject.vue"
import BackProject from '../components/BackProject.vue'

export default {
  name: "Home",
  components: {
    AboutProject,
    BackProject
  },
  data() {
    return {
      percent_baked: 89914,
      total_backers: 5007,
      days_left: 56,
      max_backable: 100000,
      min_backable: 0,
      modal: true,
      open: false
    } 
  },
  methods: {
    open_b_modal(){
      this.open = !this.open
    }
  }
}
</script>

<style scoped>
* {
  padding: 0;
  margin: 0;
  text-decoration: none;
  list-style: none;
}
.blk-n {
  display: flex;
  position: absolute;
  align-items: center;
  justify-content: center;
  background-color: rgba(0, 0, 0, 0.6);
  width: 100%;
  height: 100%;
  z-index: 2;
}
.home {
  background-color: rgb(232, 222, 214);
}
/**/
#nav {
  background-image: url("../assets/img/image-hero-desktop.jpg");
  background-repeat: no-repeat;
  width: 100%;
  height: 60vh;
  position: relative;
  display: flex;
}
nav {
  background-color: transparent;
  height: 80px;
  width: 100%;
}
label.logo {
  color: white;
  font-size: 20px;
  line-height: 80px;
  padding: 0 100px;
  font-weight: bold;
}
nav ul {
  float: right;
  margin-right: 100px;
}
nav ul li {
  display: inline-block;
  margin: 0 15px;
  align-items: center;
}
nav ul li nuxt-link {
  color: white;
}
nuxt-link {
  line-height: 80px;
}
.master-craft-cont {
  width: 100%;
  background-color: transparent;
}
.master-craft {
  position: relative;
  display: block;
  background-color: white;
  width: 50%;
  margin-top: -5%;
  margin-left: auto;
  margin-right: auto;
  text-align: center;
  justify-content: center;
  background-color: white;
  line-height: 30px;
  border-radius: 5px;
}
.mbh {
  width: 90%;
  margin: 0 auto;
}
.back {
  display: grid;
  grid-template-columns: 30% 40% 30%;
  align-items: center;
  width: 90%;
  margin: 0 auto;
}
#toggle {
  display: none;
}
#toggle + label.togglebtn {
  font-size: 30px;
  color: white;
  float: right;
  line-height: 80px;
  margin-right: 40px;
  cursor: pointer;
  display: none;
}
@media (max-width: 952px) {
  label.logo {
    padding-left: 50px;
  }
  nav ul li nuxt-link {
    font-size: 12px;
  }
}
@media (max-width: 900px) {
  #nav {
  background-image: url("../assets/img/image-hero-mobile.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  width: 100%;
  height: 55vh;
  position: relative;
  display: flex;
  }
  
  .nav-menu {
    box-sizing: border-box;
  }
  .nav-menu {
    position: relative;
  }
  .nav-menu::after {
    content: "";
    top: 100%;
    position: absolute;
    height: 2px;
    width: 280%;
    background: hsl(0, 8%, 69%);
    right: 2%;
    left: -17%;
  }
  .nav-menu:last-of-type::after{
    display: none;
  }
 
  #mc {
    top: -4;
  }
  .back {
    display: grid;
    grid-template-columns: 80% 5% 13%;
    margin: 0 auto;
  }
  #btp {
    width: 100%;
  }
  .book {
    display: grid;
    grid-template-columns: 70% 5% 25%;
    background: none;
  }
  span {
    display: none;
  }
  nav ul li nuxt-link {
    color: black;
    line-height: 65px;
    font-weight: 800;
    font-size: 14px;
  }
  .main-backed #fig-backed {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: auto;
    justify-items: center;
  }
  div.main-backed {
    height: 300px;
  }
  .fig-backed-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .fig-backed-item::after {
    display: none;
  }
  .menu {
    display: none;
  }

  #toggle + label.togglebtn {
    display: inline-block;
    background-color: transparent;
  }
  label.togglebtn i#close {
    display: none;
  }
  #toggle:checked + label.togglebtn i#bars {
    display: none;
  }
  #toggle:checked + label.togglebtn i#close {
    display: block;
    line-height: 80px;
  }
  #toggle:checked ~ .menu {
    height: auto;
    width: 50%;
    display: grid;
    grid-template-rows: auto auto auto;
    align-items: center;
    justify-content: left;
    background: white;
    border-radius: 5px;
    margin: 0 25%;
  }
}
#btp-button {
  color: white;
}
#btp, #book-m {
  margin: 20px auto;
}
.book {
  display: grid;
  grid-template-columns: 40% 20% 40%;
  align-items: center;
  background-color: rgb(232, 222, 214);
  width: 100%;
  border-radius: 20px;
  height: 40px;
}
#book-m {
  width: 2.5em;
  position: absolute;
  margin-top: 0;
}
button {
  background: none;
  border-style: none;
  color: hsl(0, 0%, 48%);
  font-weight: bold;
  display: flex;
  height: auto;
}
#bm {
  margin-left: 62px;
}
#btp {
  background-color: hsl(176, 72%, 28%);
  width: 100%;
  color: white;
  border-radius: 20px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
}
#btp:hover {
  background: hsl(176, 53%, 42%);
}
#mc {
  margin-top: -7%;
}
h4 {
  font-weight: 700;
  font-size: 22px;
}
p {
  font-size: 15px;
}
.main-backed {
  width: 50%;
  background-color: white;
  margin: 10px auto;
  border-radius: 5px;
  display: grid;
  grid-template-rows: 80% 20%;
  height: 130px;
  box-sizing: border-box;
}
#fig-backed {
  display: grid;
  grid-template-columns: auto auto auto;
  justify-items: left;
  grid-gap: 20px;
  box-sizing: border-box;
  overflow: hidden;
  width: 90%;
  margin: 15px auto;
}
.fig-backed-item {
  box-sizing: border-box;
}
.fig-backed-item {
  position: relative;
}
.fig-backed-item::after {
  content: "";
  top: 15px;
  position: absolute;
  height: 100%;
  width: 2px;
  background: hsl(0, 5%, 85%);
  right: -65%;
}
.fig-backed-item:last-child::after {
  display: none;
}
#carousel {
  display: flex;
  align-items: center;
  justify-items: center;
  height: 5px;
  margin-bottom: -50%;
}
progress[value] {
  /* Reset the default appearance */
  -webkit-appearance: none;
  appearance: none;
  width: 90%;
  margin: auto auto;
  height: 7px;
}
progress[value]::-webkit-progress-bar {
  background: hsl(0, 5%, 88%);
  border-radius: 5px;
  height: 10px;
}
progress[value]::-webkit-progress-value {
  background: hsl(176, 50%, 47%);
  border-radius: 5px;
}
.fig {
  line-height: 2.2em;
  font-weight: 800;
  font-size: 22px;
}
.fiw {
  font-size: 13px;
  color: black;
}
.nav-menu:hover {
  font-size: 1.1em;
}
</style>
