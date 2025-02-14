<script setup>
import { ref } from 'vue';
import Box from './components/Box.vue';
import Card from './components/Card.vue';
import Contact from './components/Contact.vue';
import Blockquote from './components/Blockquote.vue';
import Accordion from './components/Accordion.vue';

const options = ref({
  licenseKey: 'YOUR_KEY_HERE',
  scrollOverflow: false,
  scrollBar: false,
  menu: '#menu',
  navigation: true,
  controlArrows: false,
  navigationPosition: 'left',
  anchors: ['page1', 'page2', 'page3'],
  sectionsColor: [
    '#121619',
    '#121619',
    '#121619',
    '#121619',
    '#1bcee6',
    '#ee1a59',
    '#2c3e4f',
    '#ba5be9',
    '#b4b8ab',
  ],
});
</script>

<template>
  <div class="min-w-full absolute z-50 flex justify-between items-center px-2">
    <a href="#page1" target="_blank">
      <img src="/logo.svg" class="logo" alt="Vite logo" />
    </a>
    <div class="flex gap-8 pr-8 uppercase">
      <a href="#page2" target="_blank"> Overview </a>
      <a href="#page3" target="_blank"> Data </a>
      <a href="#page3" target="_blank"> Methods </a>
      <a href="#page3" target="_blank"> Results </a>
      <a href="#page3" target="_blank"> Team </a>
    </div>
  </div>
  <full-page :options="options" id="fullpage" ref="fullpage">
    <div class="section items-center">
      <div class="bg-img" id="title" />
      <div
        class="h-1/4 w-full absolute -z-[1] bottom-0 bg-gradient-to-t from-[#121619]"
      />
      <div class="w-full max-w-screen-xl flex flex-col gap-8">
        <div class="flex gap-8 h-full">
          <div class="w-fit align-top flex flex-col gap-8">
            <p class="text-8xl text-left font-bold">
              Follow the
              <br />
              Red Brick Road
              <br />
              and see where
              <br />it goes.
            </p>
            <p class="text-3xl font-mono text-left">
              A Data-Driven Investigation into the rampant
              <br />
              Red Tagging of Activists in the Philippines
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="section items-center">
      <div class="bg-img" id="grid" />
      <div class="max-w-screen-xl flex flex-col gap-8">
        <div class="flex justify-between items-center">
          <p class="text-8xl text-left font-extrabold">Problem Formulation</p>
          <Box
            header="Background"
            msg="Red-tagging in the Philippines has been used for decades as the government's approach to campaign against insurgencies since 1969. With the creation of NTF-ELCAC during the Duterte's administration, red-tagging became more dangerous -- dedicated and funded specifically to tracking down alleged members of CPP-NPA."
            icon="oi-telescope"
          />
        </div>
        <div class="flex gap-8">
          <Card
            header="Research Question"
            msg="Did the Duterte Administration exacerbate the problem of red-tagging in the Philippines?"
            icon="oi-search"
          />
          <Card
            header="Hypothesis"
            msg="Red-tagging of activists increased with time in the course of the Duterte administration"
            icon="oi-star"
          />
          <Card
            header="Null Hypothesis"
            msg="The red-tagging of activists did not change during the course of the Duterte Administration"
            icon="oi-skip"
          />
          <Card
            header="Action Plan"
            msg="Analyze and compare the yearly frequency of the mis/disinformation tweets that red-tag activists"
            icon="oi-terminal"
          />
        </div>
      </div>
    </div>
    <div class="section items-center">
      <div class="bg-img" id="wave" />
      <div class="w-full max-w-screen-xl flex flex-col gap-8">
        <div class="">
          <p class="text-8xl text-left font-extrabold">See the tweets</p>
        </div>
        <div class="max-w-screen-xl flex flex-row gap-8">
          <Accordion />
        </div>
      </div>
    </div>
    <div class="section items-center">
      <div class="bg-img" id="wave" />
      <div class="flex flex-col gap-8">
        <div class="">
          <p class="text-8xl text-left font-extrabold">Meet our team</p>
        </div>
        <div class="max-w-screen-xl flex flex-row gap-8">
          <Contact
            name="Mutya Gulapa"
            email="mcgulapa@up.edu.ph"
            src="mutya.jpg"
          />
          <Contact
            name="Migo Pagdanganan"
            email="avpagdanganan@up.edu.ph"
            src="migo.jpg"
          />
          <Contact
            name="Jarred Luzada"
            email="jeluzada@up.edu.ph"
            src="jarred.jpg"
          />
        </div>
      </div>
    </div>
  </full-page>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
