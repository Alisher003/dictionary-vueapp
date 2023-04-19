<template>
  <div class="container">
    <div class="product-main">
      <p class="product-main__text">{{ props.meanings.partOfSpeech }}</p>
      <span class="product-main__line"></span>
    </div>

    <div>
      <p>{{}}</p>
      <p class="product-main__heading">Meaning</p>
      <ul class="product-main__list" v-for="(definition, index) in props.meanings.definitions"
          :key="index">  
        <li class="product-main-item">
          <span></span>
          <p class="product-main__desc">{{ definition.definition }}</p>
        </li>
        <p class="product-main__desctwo">{{ definition.example }}</p>
      </ul>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["meanings"]);
console.log(props.meanings);
</script>

<style>
.product-main {
  display: flex;
  align-items: center;
  padding: 40px 0;
  gap: 24px;
}

.product-main__text {
  font-style: italic;
  font-weight: 700;
  font-size: 24px;
  line-height: 29px;
  color: #2d2d2d;
}

.product-main__line {
  display: flex;
  flex: 1;
  height: 2px;
  background: #e9e9e9;
}

.product-main__heading {
  font-style: normal;
  font-weight: 400;
  font-size: 20px;
  line-height: 24px;
  color: #757575;
}

.product-main-item {
  display: flex;
  align-items: center;
  padding: 5px 10px;
  gap: 30px;
  padding-top: 10px;
}

.product-main-item span {
  max-width: 5px;
  width: 100%;
  height: 5px;
  border-radius: 100%;
  background: #8F19E8;
  left: 20px;
}

.product-main__desc {
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 24px;
  color: #2D2D2D;
}

.product-main__desctwo {
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 24px;
  color: #757575;
  padding-left: 40px;
}
</style>
