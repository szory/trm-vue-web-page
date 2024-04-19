<template>
    <div 
        class="pomiaryContainer" 
        style="background-size: cover; background-image: url('src/assets/pexels-gustavo-fring-4254159.jpg'); background-position: 70% 26%;">
            <v-divider :thickness="80" class="border-opacity-0"></v-divider>
            <v-sheet
                class="mx-auto pa-6 bgColor"
                elevation="0"
                :max-width="vCardSize"
                :class="fontStyleClass"
                ref="pvText"
            >
                    <v-icon icon="mdi-grid"/>

                        <div v-if="isVisibleOne">
                            <p>Pomiarujemy instalacje </p>
                            <p>fotowoltaiczne</p>
                        </div>

            </v-sheet>
            <br />
            <v-sheet
                class="mx-auto pa-6 bgColor"
                elevation="0"
                :max-width="vCardSize"
                :class="fontStyleClass"
                ref="pvText"
            >
                    <v-icon icon="mdi-file-chart-outline"/>
                    <!-- <Transition name="slide-fade"> -->
                        <div  v-if="isVisibleOne">
                            <p>Dostarczamy raport o stanie</p> 
                            <p>technicznym instalacji PV</p>
                        </div>
                    <!-- </Transition> -->
            </v-sheet>
            <br>    
            <v-sheet
                class="mx-auto pa-6 bgColor"
                elevation="0"
                :max-width="vCardSize"
                :class="fontStyleClass"
                ref="pvText"
            >
                    <v-icon icon="mdi-lightbulb-on-10"/>
                    <!-- <Transition name="slide-fade"> -->
                        <div  v-if="isVisibleOne">
                            <p>Sprawdzamy parametry</p> 
                            <p>produkowanego prądu przez</p>
                            <p>instalację PV</p>
                        </div>
                    <!-- </Transition> -->
            </v-sheet>
     </div>
</template>

<script setup lang="ts">
import { computed, toRefs,onMounted,ref, type Ref,watch } from 'vue';
import { useElementVisibility } from '@vueuse/core'

const props = defineProps<{
  mobile: boolean;
  show: boolean;
}>();

const { mobile,show } = toRefs(props)
const pvText = ref(null);

const fontStyleClass = computed(()=> mobile.value?"text-h7 fontColorMine fontSize":"text-h5 fontColorMine");
const vCardSize = computed(() => mobile.value?300:600);

const isVisibleOne = useElementVisibility(pvText);

onMounted(() => {
    // console.log("hejk ",12)
})

watch(isVisibleOne,()=>{
    console.log("isVisibleOne",isVisibleOne.value)
})

</script>

<style scoped>
div.pomiaryContainer {
    height:100vh;
    width: 100vw;
    padding-left: 7px;
}
.fontColorMine{
    color: white;
}
.fontSize{
    font-weight: bolder;
}

/* .v-enter-active,
.v-leave-active {
  transition: opacity 2.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
} */

.slide-fade-enter-active {
  transition: all 0.7s ease-in;
}

.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(80px);
  opacity: 0;
}
.bgColor{
    background-color: rgba(0, 68, 255,0.6);
    text-align: center;
}

</style>