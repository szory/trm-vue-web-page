<script setup lang="ts">
import PomiaryElektr from './components/PomiaryElektr.vue'
import PomiaryPv from './components/PomiaryPv.vue'
import Projekty from './components/Projekty.vue'
import Kontakt from './components/Kontakt.vue'
import Menu from './components/Menu.vue'
import Opinie from './components/Opinie.vue'

import {onMounted,ref, type Ref} from 'vue'
import { useDisplay } from 'vuetify'


const { mobile } = useDisplay()

onMounted(() => {
    console.log(mobile.value) // false
})

const one = ref();
const two = ref();
const three = ref();
const four = ref();
const five = ref();

// function selectActiveLink(id: number){
//     const elements: [HTMLElement] = linkToOne.value.getElementsByClassName("linkElement")
//         for (let i=0;i<elements.length;i++){
//             elements[i].classList.remove('active');
//         }
//         elements[id].classList.add('active')
// }
// function scrollTo(view: Ref) { 
//   view.value?.scrollIntoView({ behavior: 'smooth' }) 
// }
</script>

<template>
<v-app>

    <!-- <div class="navigation_div" ref="linkToOne"> 
      <a class="linkElement active" @click="toOne()">Pomiary elektryczne</a>
      <a class="linkElement" @click="toTwo()">Pomiary fotowoltaiki</a>
      <a class="linkElement" @click="toThree()">Nasze Projekty</a>
      <a class="linkElement" @click="toFour()">Kontakt</a>
    </div> -->

    <Menu 
        :one=one
        :two=two
        :three=three
        :four=four
        :five="five"
    />

    <section
        id="PomiaryElektr" 
        @wheel.prevent
        @touchmove.prevent
        @scroll.prevent 
        ref="one"
    >
        <PomiaryElektr :mobile=mobile></PomiaryElektr>
    </section>
    <section 
        id="PomiaryPv" 
        @wheel.prevent
        @touchmove.prevent
        @scroll.prevent 
        ref="two"
    >
        <PomiaryPv :mobile=mobile :show="true"></PomiaryPv>
    </section>
    <section 
        @wheel.prevent
        @touchmove.prevent
        @scroll.prevent 
        ref="three"
    >
        <Projekty :mobile=mobile></Projekty>
    </section>
    <section
        @wheel.prevent
        ref="five"
    >
        <Opinie :mobile=mobile></Opinie>
    </section>
    <section 
        @wheel.prevent
        @touchmove.prevent
        @scroll.prevent 
        ref="four"
    >
        <Kontakt :mobile=mobile></Kontakt>
    </section>
    <a href="https://www.flaticon.com/free-icons/flat" title="flat icons">Flat icons created by Made by Made Premium - Flaticon</a>
</v-app>
</template>

<style scoped>

/* section {
    height:100vh;
    width: 100vw;
    padding-left: 30px;
} */
.navigation_div {
    position: fixed;
    z-index: 999;
    /* right: 1px; */

    width: 100%;
    height: 35px;
    background-color: darkolivegreen;
    /* Center horizontally*/
    margin: 0 auto;
    /* left: 45%; */
    /* right: 45%; */
}
.navigation_div a {
    display: inline-block;
    font-size: 14px;
    color: #FFF;
    text-align: center;
    /* background: #000; */
    padding: 10px;
    margin: 3px;
    cursor: pointer;
    /* width: 40px; */
}

div a.router-link-exact-active {
  color: var(--color-text);
}

div a.router-link-exact-active:hover {
  background-color: transparent;
}

.navigation_div a.active
{
    font-weight: bold;
    font-size: larger;
}

</style>