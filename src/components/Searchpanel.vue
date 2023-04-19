<template>
  <div>
    <div class="container">
      
      <form  @submit.prevent="emit('submit-word', word.trim(''))">
        <input
        type="text"
        class="form__input"
        v-model="word"
        />
        
        <!-- <button class="form__search">
            <img src="../assets/img/search.png" alt="icon" />
        </button> -->
        
      </form>
      
    </div>
  </div>
</template>

<script setup>
  import { ref } from "vue";  
  const emit = defineEmits(["submit-word"]);
  const word = ref("");
</script>

<style lang="scss">
.form {
  width: 100%;
  position: relative;
}

.form.error input {
  border: 1px solid var(--red);
}

.form.error span {
  display: block;
  margin-top: 8px;
}

.form span {
  display: none;
  transition: var(--transition);
}

.form__input {
  padding: 20px 24px;
  padding-right: 45px;
  width: 100%;
  font-weight: bold;
  font-family: inherit;
  font-size: 20px;
  line-height: 24px;
  background: var(--gray-light);
  border: 1px solid var(--gray-light);
  border-radius: var(--radius);
  transition: var(--transition);
}

.form__input[placeholder] {
  color: var(--black-2d);
}

.form__input:focus {
  border: 1px solid var(--purple);
}

.form__search {
  position: absolute;
  top: 24px;
  right: 24px;
  cursor: pointer;
  background: transparent;
  border: none;
  transition: var(--transition);
}

.form__search:hover {
  transform: scale(1.04) translateY(-1px);
}

body[data-theme="dark"] .form__input {
  border: 1px solid var(--black-1f);
  background: var(--black-1f);
}

.content__top {
  margin-top: 45px;
  display: flex;
  justify-content: space-between;
}

.word__name {
  font-weight: 700;
  font-size: 64px;
  line-height: 77px;
  color: var(--black-2d);
}

.word__read {
  padding-top: 8px;
  font-weight: 400;
  font-size: 24px;
  line-height: 29px;
  color: #a445ed;
  display: block !important;
}

.audio-button {
  width: 75px;
  height: 75px;
  padding: 20px;
  padding-left: 25px;
  margin-top: 20px;
  border-radius: 50px;
  justify-content: center;
  background: transparent;
  border: none;
  display: none;
  transition: 0.3s all ease;
  background: #a445ed;
  mix-blend-mode: normal;
  opacity: 0.25;
  cursor: pointer;
}

.audio-button:hover {
  background: #a445ed;
  opacity: 1;
}

.audio-button__image path {
  fill: #a445ed;
}

.noun {
  display: none;
  position: relative;
  margin-top: 40px;
}

.noun__heading,
.verb__heading {
  margin-bottom: 40px;
  font-style: italic;
  font-weight: 700;
  font-size: 24px;
  line-height: 29px;
  color: var(--black-2d);
}

.noun__heading:after {
  position: absolute;
  top: 15px;
  left: 160px;
  content: "";
  display: block;
  width: 70%;
  border: 1px solid #e9e9e9;
}

.noun__meaning,
.verb__meaning {
  padding-bottom: 25px;
  font-weight: 400;
  font-size: 20px;
  line-height: 24px;
  color: var(--black-2d);
}

.noun__definition,
.verb__definition {
  padding-bottom: 15px;
  padding-left: 35px;
  font-weight: 400;
  font-size: 18px;
  line-height: 24px;
  color: var(--black-2d);
}

.synonyms,
.antonyms {
  display: flex;
  padding-top: 25px;
  display: none;
}

.synonyms__noun,
.antonyms__noun {
  padding-left: 22px;
  font-weight: 700;
  font-size: 20px;
  line-height: 24px;
  color: #a445ed;
}

.verb {
  position: relative;
}

.verb__example {
  padding-left: 35px;
  font-weight: 400;
  font-size: 18px;
  line-height: 24px;
  color: var(--black-2d);
}

.line {
  margin-top: 40px;
  margin-bottom: 30px;
  width: 100%;
  height: 1px;
  display: block;
  content: "";
  background: #e9e9e9;
}

.source {
  display: flex;
  padding-bottom: 100px;
}

.source__paragraph {
  font-weight: 400;
  font-size: 14px;
  line-height: 17px;
  text-decoration-line: underline;
  color: var(--black-2d);
}

.source__link {
  padding-left: 20px;
  text-decoration: none;
  font-weight: 400;
  font-size: 14px;
  line-height: 17px;
  text-decoration-line: underline;
  color: var(--black-2d);
}

.on-off {
  margin-top: 14px;
  background: transparent;
  border: none;
}

.on {
  color: #ffffff !important;
  background: #1f1f1f;
}

.white {
  color: #ffffff;
}

.error {
  text-align: center;
  display: none;
}

.error__emotion {
  margin-bottom: 40px;
  width: 30px;
  font-weight: 400;
  font-size: 64px;
  line-height: 75px;
  color: #2d2d2d;
}

.error__paragraph {
  padding-top: 40px;
  font-weight: 700;
  font-size: 20px;
  line-height: 24px;
  text-align: center;
  color: var(--black-2d);
}

.error__suggestion {
  padding-top: 24px;
  font-weight: 400;
  font-size: 18px;
  line-height: 24px;
  text-align: center;
  color: var(--black-2d);
}

h1,
h2,
h3 h4,
p {
  padding: 0;
  margin: 0;
}
</style>
