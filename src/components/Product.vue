<template>
  <div class="container">
    <div class="product-nav">
      <h3 class="product-nav__heading">{{ word.word }}</h3>
      <button class="audio" @click="audioPlay">
        <i class="fa-sharp fa-solid fa-play"></i>
        <i class="fa-solid fa-pause"></i>
      </button>
    </div>
    <p class="product-nav__text">{{ word.phonetic }}</p>
  </div>
</template>

<script setup>
import { ref } from "vue";
const props = defineProps(["word"]);

function audioPlay() {
  let audio = ref("");
  props.word.phonetics.map((phonetic) => {
    if (phonetic.audio) {
      audio.value = new Audio(phonetic.audio);
    }
  });

  audio.value.play();
}
</script>

<style>
.product-nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 45px 0 8px;
}

.product-nav__heading {
  font-family: 'Inter';
  font-style: normal;
  font-weight: 700;
  font-size: 64px;
  line-height: 77px;
  color: #2D2D2D;
  margin: 0;
}

.audio {
  width: 75px;
  height: 75px;
  border-radius: 50%;
  display: block;
  align-items: center;
  justify-content: center;
  background: rgba(164, 69, 237, 0.1450980392);
  transition: var(--transition);
  cursor: pointer;
}

.product-nav__text {
  font-style: normal;
  font-weight: 400;
  font-size: 24px;
  line-height: 29px;
  color: #A445ED;
}

.audio:hover {
  background: var(--purple);
}

.audio:hover i {
  color: var(--white);
}

.audio:hover i.fa-play {
  display: none;
}

.audio:hover i.fa-pause {
  display: block;
}
.audio i {
  font-size: 21px;
  color: var(--purple);
  transition: var(--transition);
  margin-left: 4px;
}
.audio i.fa-play {
  display: block;
}
.audio i.fa-pause {
  font-size: 23px;
  margin-left: 0;
  display: none;
}
</style>
