<template>
    <div style="background-size: cover; background-image: url('src/assets/pexels-pixabay-163073.jpg'); background-position: 70% 26%;">
        <div style="position: relative; top:100px;margin-left: 100px;  width: 800px; height: 500px; opacity: 0.7;">
            <v-card
            variant="elevated"
            :max-width=vCardSize
            height="155"
            style="background-color: beige;"
            >
                <v-card-text :class="fontStyleClass" style="color: #004b7c">
                    <p>Tworzymy autorskie urządzenia</p> 
                    <br/>
                    <p>do monitorowania zużycia oraz</p> 
                    <br/>
                    <p>produkcji energii elektrycznej</p>
                </v-card-text>
            </v-card>
        </div>
    </div>
</template>

<script setup lang="ts">
import { computed, toRefs } from 'vue';

const props = defineProps<{
  mobile: boolean;
}>();

const { mobile } = toRefs(props)

const fontStyleClass = computed(()=> mobile.value?"text-h7 fontColorMine fontSize":"text-h4 fontColorMine");
const vCardSize = computed(()=> mobile.value?233:544);
</script>

<style scoped>
div {
    height:100vh;
    width: 100vw;
    padding-left: 5px;
}
ul li {
  margin: 19px;
}
.fontColorMine{
    color: white;
}
.fontSize{
    font-weight: bolder;
}
</style>