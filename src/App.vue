<script>
/* import HeaderBambey from "./HeaderBambey.vue";
import FooterBambey from "./FooterBambey.vue";
import Formulaire from "./Formulaire.vue" ;
import VueTabulaire from "./VueTabulaire.vue" ; */
import UpApplication from './UpApplication.vue';

export default {
  components: {
  /*  HeaderBambey,
    FooterBambey,
    Formulaire,
    VueTabulaire, */
    UpApplication,
  }
}
</script>

<template>
<header-bambey/>
 <formulaire/>
 <br/>
 <vue-tabulaire/>
 <footer-bambey/>
 <UpApplication/>
</template>

<style scoped></style>
