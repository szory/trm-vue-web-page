<template>

<v-app-bar
        color="primary"
        prominent
    >
        <v-app-bar-nav-icon variant="text" @click.stop="drawer = !drawer">
        </v-app-bar-nav-icon>
        <v-toolbar-title>
            {{ titleSite }}
            <!-- <span v-if="isVisibleOne">{{titlePomElektr}}</span>
            <span v-if="isVisibleTwo">{{titlePomPv}}</span>
            <span v-if="isVisibleThree">{{titleOurProj}}</span>
            <span v-if="isVisibleFour">{{titleContact}}</span>
            <span v-if="isVisibleFive">{{titleOpinie}}</span> -->
        </v-toolbar-title>
    </v-app-bar>

    <v-navigation-drawer
        v-model="drawer"
        location="bottom"
        temporary
      >
        <v-list>
            <v-list-item
            key="index1"
            value="index1"
            >
                <v-list-item-title @click="toOne()">
                    {{titlePomElektr}}
                </v-list-item-title>
            </v-list-item>
            <v-list-item
            key="index1"
            value="index1"
            >
                <v-list-item-title @click="toTwo()">
                    {{titlePomPv}}
                </v-list-item-title>
            </v-list-item>
            <v-list-item
            key="index1"
            value="index1"
            >
                <v-list-item-title @click="toThree()">
                    {{titleOurProj}}
                </v-list-item-title>
            </v-list-item>
            <v-list-item
            key="index1"
            value="index1"
            >
                <v-list-item-title @click="toFive()">
                    {{titleOpinie}}
                </v-list-item-title>
            </v-list-item>

            <v-list-item
            key="index1"
            value="index1"
            >
                <v-list-item-title @click="toFour()">
                    {{titleContact}}
                </v-list-item-title>
            </v-list-item>
        </v-list>
    </v-navigation-drawer>

</template>

<script setup lang="ts">

import {ref, type Ref, toRefs, watch, computed, watchEffect, onMounted }  from 'vue'
import { useElementVisibility } from '@vueuse/core'

const props = defineProps<{
  one: Ref;
  two: Ref;
  three: Ref;
  four: Ref;
  five: Ref;
}>();

const elementIsVisibleInViewport = (el: HTMLElement, partiallyVisible = false) => {
  const { top, left, bottom, right } = el.getBoundingClientRect();
  const { innerHeight, innerWidth } = window;
  return partiallyVisible
    ? ((top > 0 && top < innerHeight) ||
        (bottom > 0 && bottom < innerHeight)) &&
        ((left > 0 && left < innerWidth) || (right > 0 && right < innerWidth))
    : top >= 0 && left >= 0 && bottom <= innerHeight && right <= innerWidth;
};

const { one, two,three,four, five} = toRefs(props);

const isVisibleOne = useElementVisibility(one);
const isVisibleTwo = useElementVisibility(two);
const isVisibleThree = useElementVisibility(three);
const isVisibleFour = useElementVisibility(four);
const isVisibleFive = useElementVisibility(five);

const titlePomElektr = ref("Pomiary elektryczne")
const titlePomPv = ref("Pomiary fotowoltaiki")
const titleOurProj = ref("Nasze Projekty")
const titleContact = ref("Kontakt")
const titleOpinie = ref("Klienci o nas")
const titleSite = ref(titlePomElektr.value);

const drawer = ref(false);

function toOne() {
    one.value.scrollIntoView({behavior: 'smooth' });
    //selectActiveLink(0);
    drawer.value=false;
    titleSite.value = titlePomElektr.value;
 
    const { top, left, bottom, right } = one.value.getBoundingClientRect();
    console.log(top,left,bottom,right)
}

function toTwo() {
    two.value.scrollIntoView({ behavior: 'smooth' });
    //selectActiveLink(1);
    drawer.value=false;
    titleSite.value = titlePomPv.value;
}

function toThree() {
    three.value.scrollIntoView({ behavior: 'smooth' });
    //selectActiveLink(2);
    drawer.value=false;
    titleSite.value = titleOurProj.value;
}
 
function toFour() {
    four.value.scrollIntoView({ behavior: 'smooth' });
    //selectActiveLink(3);
    drawer.value=false;
    titleSite.value = titleContact.value;
}

function toFive() {
    five.value.scrollIntoView({ behavior: 'smooth' });
    //selectActiveLink(3);
    drawer.value=false;
    titleSite.value = titleOpinie.value;
}

watchEffect(()=>{
    // console.log(one.value);
    
})

onMounted(() => {
    // console.log("hejk ",one.value.getElementById("PomiaryElektr"))
})

</script>

<style scoped>
</style>