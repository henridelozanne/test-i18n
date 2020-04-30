<template>
  <div id="app">
    <h1>{{ $t('whoAmI') }}</h1>
    <div class="btn-ctn">
      <button @click="setLanguage('en')">{{ $t('languages.english') }}</button>
      <button @click="setLanguage('fr')">{{ $t('languages.french') }}</button>
      <button @click="setLanguage('es')">{{ $t('languages.spanish') }}</button>
    </div>
    <span class="current">{{ $t('current') }} : {{ currentLanguage }}</span>
  </div>
</template>

<script>
import i18n from './i18n';

export default {
  name: 'App',
  data() {
    return {
      currentLanguage: 'en',
    };
  },
  methods: {
    setLanguage(language) {
      this.currentLanguage = language;
      i18n.locale = language;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.btn-ctn {
  width: 70%;
  margin: 100px auto;
  display: flex;
  justify-content: space-around;
}

button {
  padding: 5px 10px;
  background: teal;
  color: white;
  font-size: 18px;
  border-radius: 5px;
  cursor: pointer;
}
</style>
