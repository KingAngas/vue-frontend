<script>
</script>

<template>
<form id="item-form">
  <input type="hidden" id="item-id" />


  <label for="name">Nom</label>
  <input id="name" placeholder="Nom" required />


  <label for="prenom">Prénom</label>
  <input id="prenom" placeholder="Prenom" required />


  <div style="display: flex; gap: 10px;">
    <button type="submit">Enregistrer</button>
    <button type="button" onclick="resetForm()">Annuler</button>
  </div>
</form>

</template>

<style scoped></style>