<template>
  <div class="sign-in">
    <div class="sign-in__info">
      <LogoHeader name="PNFT Market"/>
      <FormVue msg="Welcome to Your Vue.js App"/>
      <CopyrightFooter />
    </div>
    <div class="sign-in__bg">
      <BagraundImg />
    </div>
  </div>
  
</template>

<script>
import LogoHeader from './components/LogoHeader.vue';
import FormVue from './components/FormVue.vue';
import BagraundImg from './components/BagraundImg.vue';
import CopyrightFooter from './components/CopyrightFooter.vue';


export default {
  name: 'App',
  components: {
    LogoHeader,
    FormVue,
    BagraundImg,
    CopyrightFooter
}
}
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

</style>
