<template>
    <div style="background-size: cover; background-image: url('src/assets/pexels-gustavo-fring-4254159.jpg'); background-position: 70% 26%;">
        <!-- <div style="position: relative; top:100px;margin-left: 100px;  width: 500px; height: 500px; color: rgb(0, 68, 255)"> -->
        <div style="position: relative; top:100px;margin-left: 100px;  width: 800px; height: 500px; opacity: 0.6;">
            <v-card
            height="100"
            variant="elevated"
            :max-width=vCardSize
            style="background-color: rgb(0, 68, 255);"
            ref="pvText"
            >
                <v-card-text :class="fontStyleClass">
                    <Transition name="slide-fade">
                        <div  v-if="isVisibleOne">
                            <p>Pomiarujemy instalacje </p>
                            <br/> 
                            <p>fotowoltaiczne</p>
                        </div>
                    </Transition>
                </v-card-text>
            </v-card>
            <br>    
            <v-card
            variant="elevated"
            :max-width=vCardSize
            style="background-color: rgb(0, 68, 255);"
            height="100"
            >
                <v-card-text :class="fontStyleClass">
                    <Transition name="slide-fade">
                        <div  v-if="isVisibleOne">
                            <p>Dostarczamy raport o stanie</p> 
                            <br/>
                            <p>technicznym instalacji PV</p>
                        </div>
                    </Transition>
                </v-card-text>
            </v-card>
            <br>    
            <v-card
            variant="elevated"
            :max-width=vCardSize
            style="background-color: rgb(0, 68, 255);"
            height="140"
            >
                <v-card-text :class="fontStyleClass">
                    <Transition name="slide-fade">
                        <div  v-if="isVisibleOne">
                            <p>Sprawdzamy parametry</p> 
                            <br/>
                            <p>produkowanego prądu przez</p>
                            <br/>
                            <p>instalację PV</p>
                        </div>
                    </Transition>
                </v-card-text>
            </v-card>
        
        </div>
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

const fontStyleClass = computed(()=> mobile.value?"text-h7 fontColorMine fontSize":"text-h4 fontColorMine");
const vCardSize = computed(() => mobile.value?220:544);

const isVisibleOne = useElementVisibility(pvText);

onMounted(() => {
    // console.log("hejk ",12)
})

watch(isVisibleOne,()=>{
    console.log("isVisibleOne",isVisibleOne.value)
})

</script>

<style scoped>
div {
    height:100.1vh;
    width: 100vw;
    padding-left: 5px;
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

</style>