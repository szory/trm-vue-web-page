<template>
    <div style="
    background-size: cover; 
    background-image: url('src/assets/pexels-fauxels-3184435.jpg');
    background-position: 70% 26%;
     ">
        <div style="position: relative; top:100px;margin-left: 100px;  width: 800px; height: 500px; color: chocolate">
            <v-card
            :max-width=vCardWidthSize
            :height=vCardHeightSize 
            >
            <!-- "275" -->
                <v-card-text :class="fontStyleClass">    
                    <p>Zadzwoń lub napisz do nas</p> 
                    <br/>
                    <br v-if="!mobile"/>
                    <p><v-icon icon="mdi-phone"/> 509 392 617</p> 
                    <br/>
                    <p>
                        <v-icon icon="mdi-phone"/> 502 549 900
                    </p>
                    <br>
                    <p>
                        <v-icon icon="mdi-email"/> trm.elektryka@gmail.com
                    </p>
                </v-card-text>
            </v-card>
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref,computed, toRefs } from 'vue';

const props = defineProps<{
  mobile: boolean;
}>();

const { mobile } = toRefs(props)

const fontStyleClass = computed(()=> mobile.value?"fontColorMine text-h7 fontSize":"fontColorMine text-h4");
const vCardWidthSize = computed(()=> mobile.value?225:505);
const vCardHeightSize = computed(()=> mobile.value?170:275);
</script>

<style scoped>
div {
    height:100vh;
    width: 100vw;
    /* padding-left: 7px; */
}
ul li {
  margin: 19px;
}
.fontColorMine{
    color: black;
}
.fontSize{
    font-weight: bolder;
}
</style>