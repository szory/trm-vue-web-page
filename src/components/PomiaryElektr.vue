<template>
    <div style="
        background-size: cover; 
        background-image: url('src/assets/pexels-onics-energy-14319099.jpg');
        background-position: 70% 26%;
        "
        class="fullscreen"
    >
        <div class="fullscreen" style="position: relative; top:100px; margin-left: 100px; width: 900px;">
            <v-row dense>
                <v-col :cols="vColSize">
                    <v-hover>
                    <template v-slot:default="{ isHovering, props }">
                    <v-card
                    v-bind="props"
                    variant="text"
                    :max-width=vCardSize
                    :height=vCardSize
                    :width=vCardSize
                    :class ="isHovering ? 'iconsIsHover': 'icons'" 
                    >
                        <v-img
                        :width="550"
                        aspect-ratio="16/9"
                        src="src/assets/house.png"
                        >
                            <v-expand-transition>
                                <div
                                v-if="isHovering"
                                class="d-flex transition-fast-in-fast-out bg-orange-darken-2 v-card--reveal pa-3"
                                :class="vFontSize"
                                style="height: 100%; text-align: center;"
                                >
                                pomiary domów
                                </div>
                            </v-expand-transition>
                        </v-img>
                    </v-card>
                    </template>
                    </v-hover>
                </v-col>
                <v-col :cols="vColSize">
                    <v-hover>
                    <template v-slot:default="{ isHovering, props }">
                    <v-card
                    v-bind="props"
                    variant="elevated"
                    :max-width=vCardSize
                    :height=vCardSize
                    :width=vCardSize
                    :class ="isHovering ? 'iconsIsHover': 'icons'" 
                    >
                        <v-img
                        :width="550"
                        aspect-ratio="16/9"
                        
                        src="src/assets/flat.png"
                        >
                            <v-expand-transition>
                                <div
                                v-if="isHovering"
                                class="d-flex transition-fast-in-fast-out bg-orange-darken-2 v-card--reveal pa-3"
                                :class="vFontSize"
                                style="height: 100%;text-align: center;"
                                >
                                pomiary mieszkań
                                </div>
                            </v-expand-transition>
                        </v-img>
                    </v-card>
                </template>
                    </v-hover>
                </v-col>
            </v-row>
            <br />
            <v-row dense>
                <v-col :cols="vColSize">
                    <v-hover>
                        <template v-slot:default="{ isHovering, props }">

                    <v-card
                    variant="elevated"
                    :max-width=vCardSize
                    :height=vCardSize
                    :width=vCardSize
                    :class ="isHovering ? 'iconsIsHover': 'icons'" 
                    v-bind="props"
                    >
                        <v-img
                        :width="550"
                        aspect-ratio="16/9"
                        
                        src="src/assets/factory.png"
                        >
                            <v-expand-transition>
                                <div
                                v-if="isHovering"
                                class="d-flex transition-fast-in-fast-out bg-orange-darken-2 v-card--reveal pa-3"
                                :class="vFontSize"
                                style="height: 100%;text-align: center;"
                                >
                                pomiary zakładów produkcyjnych
                                </div>
                            </v-expand-transition>
                        </v-img>

                    </v-card>
                        </template>
                    </v-hover>
                </v-col>
                <v-col :cols="vColSize">
                    <v-hover>
                        <template v-slot:default="{ isHovering, props }">
                    <v-card
                    variant="elevated"
                    :max-width=vCardSize
                    :height=vCardSize
                    :width=vCardSize
                    :class ="isHovering ? 'iconsIsHover': 'icons'" 
                    v-bind="props"
                    >
                        <v-img
                        :width="550"
                        aspect-ratio="16/9"
                        
                        src="src/assets/shop.png"
                        >
                            <v-expand-transition>
                                <div
                                v-if="isHovering"
                                class="d-flex transition-fast-in-fast-out bg-orange-darken-2 v-card--reveal pa-3"
                                :class="vFontSize"
                                style="height: 100%;text-align: center;"
                                >
                                pomiary punktów usługowych
                                </div>
                            </v-expand-transition>                
                        </v-img>

                    </v-card>
                    </template>
                    </v-hover>
                </v-col>
            </v-row>
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
const vCardSize = computed(()=> mobile.value?125:250);
const vColSize = computed(()=> mobile.value?2:4);
const vFontSize = computed(()=> mobile.value?"text-h7":"text-h4");
</script>

<style scoped>
div.fullscreen {
    height:101vh;
    width: 100vw;
    padding-left: 5px;
}
.icons{
    background-color: white; opacity: 0.5
}
.iconsIsHover{
    background-color: white; opacity: 1
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