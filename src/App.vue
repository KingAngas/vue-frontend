<script>
import HeaderBambey from "./HeaderBambey.vue";
import FooterBambey from "./FooterBambey.vue";
import Formulaire from "./Formulaire.vue" ;
import VueTabulaire from "./VueTabulaire.vue" ;
export default {
  components: {
    HeaderBambey,
    FooterBambey,
    Formulaire,
    VueTabulaire,
  }
}
</script>

<template>
<header-bambey/>
 <formulaire/>
 <br/>
 <vue-tabulaire/>
 <footer-bambey/>
</template>

<style scoped></style>