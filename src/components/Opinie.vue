<template>
<div class="opinionContainer" style="
    background-size: cover; 
    background-image: url('src/assets/pexels-anna-shvets-5711932.jpg');
    background-position: 70% 46%;
    "
  >
    <v-sheet
    class="mx-auto"
    elevation="0"
    max-width="1200"
    style="position: relative; top:20%;margin-left: 100px;opacity: 1;"
    >
    <v-slide-group
      v-model="model"
      class="pa-4"
      show-arrows
      style="opacity: 1;"
    >
      <!-- selected-class="bg-success" -->

    <v-slide-group-item
        v-for="n in 18"
        :key="n"
       >
          <!-- color="grey-lighten-1" -->

      <v-card
          :class="['ma-4']"
          height="180"
          width="180"
          variant="text"
        >
          <div class="d-flex fill-height align-top justify-center pa-2" style="font-size: 13px; background-color: white;color: #004b7c">
            {{ authors[n] }}
            <br /><br />
            {{ opinions[n] }}
          </div>
        </v-card>
      </v-slide-group-item>
    </v-slide-group>
  </v-sheet>

  <br>

  <!-- <v-card
  width="300"
  height="300"
  >
    <div style=
    "
      /* height:15vh;
      width: 10vw; */
      background-color: transparent;
      background-size: cover; 
      background-image: url('src/assets/Oferteo-Najlepsi-2024.png');
      /* background-position: 70% 46%; */
    "
    ></div>
  </v-card> -->

  <div :class="fixedOferteoPosition">
       <v-img
        :aspect-ratio="1"
        class="bg-white"
        src="src/assets/Oferteo-Najlepsi-2024.png"
        width="200"
        cover
      ></v-img>
    </div>

  <!-- <span style="
  height:100px;
  width: 100px;
  background-size: cover; 
  background-image: url('src/assets/Oferteo-Najlepsi-2024.png');
  background-position: 70% 46%;
  "
  ></span> -->
</div>

</template>
<script setup lang="ts">
import {ref, toRefs, computed} from 'vue'

const authors = [
  'Tomasz K'
,'Małgorzata R'
,'Paweł K'
,'Marek M'
,'Patrycja M'
,'Tadeusz M'
,'Marian O'
,'Marek M'
,'Adam B'
,'Katarzyna R'
,'Krzysiek M'
,'Artur B'
,'Robert S'
,'Adam M'
,'Sabina'
,'Izabela J'
,'Sabina S'
,'Igor B'
,'Tomasz S',
,'Pawel P'
]

const opinions = [
  'Polecam Pana Piotra, szybko, profesjonalnie z należytą starannością.',
  'Pan Piotr to wspaniały fachowiec, punktulany, rzetelny, pracowity. Wspaniale wykonał zadanie, które zostało mu powierzone-pomiary elektryczne. Polecam serdecznie',
'Super kontakt, wszystko wykonane prawidłowo, polecam wszystkim!',
'Fachowa profesjonalna usługa a przy tym niska cena. Takiej firmy szukałem. Polecam wszystkim.',
'Jestem bardzo zadowolona ze współpracy, profesjonalne podejście do klienta. Pomoc na każdym etapie pracy szczególnie z załatwianiem papierów. Polecam, firma godna polecenia.',
'Bardzo sumienna, szybka i fachowa usługa. Chciałbym aby wszystkie firmy tak funkcjonowały , gorąco polecam .',
'Zlecona usługa wykonana profesjonalnie.W trakcie realizacji usługi skorzystałem z doradztwa technicznego dotyczącego zainstalowanego osprzętu.Firma godna zaufania.',
'Bardzo miła i kompetentna obsługa zlecenia. Najniższa cena z otrzymanych ofert jakie otrzymałem ale i WYSOKA JAKOŚĆ USŁUGI. Polecam firmę jak najbardziej.',
'Miło, szybko,sprawnie i w pełni profesjonalnie',
'Dobrze wykonana robota przez fachowca . Szybko podjęli się pracy',
'Dzięki za dobrą robotę. Pełen profesjonalizm i wysoka kultura osobista. Szybka i fachowa pomoc. Jestem bardzo zadowolony.',
'Wizyta umówiona na czas! Przyjazd na czas, usługa wykonana szybko i poprawnie - polecam.',
'Po miesiącach użerania się z pseudofachowcami udało nam się trafić na firmę P. Piotra. W ciągu jednego dnia dokończył i poprawił instalację, wszystko odbyło się totalnie bezproblemowo, w super cenie i przemiłej atmosferze, polecam.',
'Profesjonalizm, znajomość zagadnień, rzetelna ocena.',
'Panowie profesjonalnie i sprawnie wykonali wszystkie zlecone im prace. Zdecydowanie polecam.',
'Szybko i sprawnie usunięto awarię związaną z brakiem prądu.',
'Panowie bardzo sprawnie i profesjonalnie wykonali zlecone prace. Polecam !',
'Sprawnie i konkretnie, dobra współpraca. Polecam.',
'Firma godna polecenia w zakresie usług elektrycznych.'
,'Bardzo szybko i sprawnie rozwiązali problem, pojawili się w przeciągu godziny od zgłoszenia. Polecam gorąco, szybko, rzetelnie i sprawnie.'
]

const model = ref(null);

const props = defineProps<{
  mobile: boolean;
}>();

const { mobile } = toRefs(props)


const fontStyleClass = computed(()=> mobile.value?"fontColorMine text-h7 fontSize":"fontColorMine text-h4");
const vCardSize = computed(()=> mobile.value?208:544);
const fixedOferteoPosition = computed(()=> mobile.value?"oferteoPositionMobile":"oferteoPosition");
</script>

<style scoped>
div.opinionContainer {
    height:100vh;
    width: 100vw;
    padding-left: 7px;
}

.oferteoPosition {
  position: relative;
  top: 20%;
  left: 40%;
}

.oferteoPositionMobile {
  position: relative;
  top: 20%;
  left: 22%;
}
</style>