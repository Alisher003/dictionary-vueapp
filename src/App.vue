<template>
  <Dictionarynav />
  <Searchpanel @submit-word="getDefinition" />
  <Product :word="definition" />
  <ProductMain
    v-for="(meaning, index) in definition.meanings"
    :key="index"
    :meanings="meaning"
  />
</template>

<script setup>
import Dictionarynav from "./components/Dictionarynav.vue";
import Searchpanel from "./components/Searchpanel.vue";
import Product from "./components/Product.vue";
import ProductMain from "./components/Product-main.vue";
import { ref, shallowRef } from "vue";
const definition = shallowRef([]);

async function getDefinition(word) {
  const url = `https://api.dictionaryapi.dev/api/v2/entries/en`;
  const req = await fetch(`${url}/${word}`);
  const data = await req.json();
  definition.value = data[0];
}


</script>

<style></style>
