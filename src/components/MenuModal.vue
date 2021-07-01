<template>
  <div class="modal">
    <div class="menu-items">
        <img @click="closeMenu()"  id="close-icon" src="../assets/img/icon-close-menu.svg" alt=""/>
        <div class="menu-container">
            <ul class="menu">
                <li class="nav-menu">About</li>
                <li class="nav-menu">Discover</li>
                <li class="nav-menu">Get Started</li>
            </ul>
        </div>
    </div>
  </div>
</template>

<script scoped>
export default {
    props: ['menuIcon', 'menuModal'],
    data() {
        return {
            hide: true
        }
    },
    methods: {
        closeMenu() {
           this.$emit('update:menuModal', false)
           this.$emit('update:menuIcon', true)
        }
    }
}
</script>

<style>
.modal {
    display: flex;
    justify-content: center;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.3);
    z-index: 4;
}
.menu-items {
    margin-top: 3%;
    width: 80%;
    background-color: transparent;
    height: 30vh;
}
#close-icon {
    margin-top: 7%;
    margin-left: 100%;
}
.logo {
    color: white;
    font-weight: 1000;
    font-size: 25px;
}
ul {
    display: flex;
    flex-direction: column;
    background: white;
    margin-top: 15%;
    border-radius: 5px;
}
ul li {
    list-style-type: none;
    color: black;
    line-height: 4em;
    font-weight: bold;
}
ul li:hover {
    color: rgb(92, 86, 86);
}
.nav-menu:first-of-type, .nav-menu:nth-of-type(2) {
    border-bottom: 1px solid rgb(233, 223, 223);
    margin-left: -2.48em;
    padding-left: 2em;
}
.nav-menu {
    margin-left: -2.48em;
    padding-left: 2em;
}
</style>