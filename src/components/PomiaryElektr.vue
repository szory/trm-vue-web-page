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
                <v-col :cols="4">
                    <v-hover>
                    <template v-slot:default="{ isHovering, props }">
                    <v-card
                    v-bind="props"
                    variant="text"
                    :max-width=vCardSize
                    height="250"
                    :class ="isHovering ? 'iconsIsHover': 'icons'" 
                    >
                    <!-- <v-card-text :class="fontStyleClass" style="color: #004b7c">
                            <ul>Wykonujemy pomiary:
                                <li>mieszkań,</li>
                                <li>domów,</li>
                                <li>zakładów produkcyjnych,</li>
                                <li>punktów handlowych</li>
                            </ul>
                        </v-card-text> -->
                        <v-img
                        :width="550"
                        aspect-ratio="16/9"
                        
                        src="src/assets/house.png"
                        >
                            <v-expand-transition>
                                <div
                                v-if="isHovering"
                                class="d-flex transition-fast-in-fast-out bg-orange-darken-2 v-card--reveal text-h2"
                                style="height: 100%;"
                                >
                                pomiary domów
                                </div>
                            </v-expand-transition>
                        </v-img>
                    </v-card>
                    </template>
                    </v-hover>
                </v-col>
                <v-col :cols="4">
                    <v-hover>
                    <template v-slot:default="{ isHovering, props }">
                    <v-card
                    v-bind="props"
                    variant="elevated"
                    :max-width=vCardSize
                    height="250"
                    :class ="isHovering ? 'iconsIsHover': 'icons'" 
                    >
                        <!-- <v-card-text :class="fontStyleClass" style="color: #004b7c">
                            <p>Dostarczamy dokumentację po</p> 
                            <br/>
                            <p>pomiarach zgodną z wymogami</p> 
                            <br/>
                            <p>ubezpieczycieli</p>
                        </v-card-text> -->
                        <v-img
                        :width="550"
                        aspect-ratio="16/9"
                        
                        src="src/assets/flat.png"
                        >
                            <v-expand-transition>
                                <div
                                v-if="isHovering"
                                class="d-flex transition-fast-in-fast-out bg-orange-darken-2 v-card--reveal text-h2"
                                style="height: 100%;"
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
            <v-col :cols="4">
                <v-hover>
                    <template v-slot:default="{ isHovering, props }">

                <v-card
                variant="elevated"
                :max-width=vCardSize
                height="250"
                :class ="isHovering ? 'iconsIsHover': 'icons'" 
                v-bind="props"
                >
                    <!-- <v-card-text :class="fontStyleClass" style="color: #004b7c">
                        <p>Dostarczamy dokumentację po</p> 
                        <br/>
                        <p>pomiarach zgodną z wymogami</p> 
                        <br/>
                        <p>ubezpieczycieli</p>
                    </v-card-text> -->
                    <v-img
                    :width="550"
                    aspect-ratio="16/9"
                    
                    src="src/assets/factory.png"
                    >
                        <v-expand-transition>
                            <div
                            v-if="isHovering"
                            class="d-flex transition-fast-in-fast-out bg-orange-darken-2 v-card--reveal text-h4"
                            style="height: 100%;"
                            >
                            pomiary zakładów produkcyjnych
                            </div>
                        </v-expand-transition>
                    </v-img>

                </v-card>
                    </template>
                </v-hover>
            </v-col>
            <!-- <br /> -->
            <v-col :cols="4">
                <v-hover>
                    <template v-slot:default="{ isHovering, props }">

                <v-card
                variant="elevated"
                :max-width=vCardSize
                height="250"
                :class ="isHovering ? 'iconsIsHover': 'icons'" 
                v-bind="props"
                >
                    <!-- <v-card-text :class="fontStyleClass" style="color: #004b7c">
                        <p>Dostarczamy dokumentację po</p> 
                        <br/>
                        <p>pomiarach zgodną z wymogami</p> 
                        <br/>
                        <p>ubezpieczycieli</p>
                    </v-card-text> -->
                    <v-img
                    :width="550"
                    aspect-ratio="16/9"
                    
                    src="src/assets/shop.png"
                    >
                        <v-expand-transition>
                            <div
                            v-if="isHovering"
                            class="d-flex transition-fast-in-fast-out bg-orange-darken-2 v-card--reveal text-h3"
                            style="height: 100%;"
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
const vCardSize = computed(()=> mobile.value?239:250);
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