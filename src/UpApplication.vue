<!-- <template>
  <div class="container">
    <p>Application: {{ informations.name }}</p>
     <p>Description: {{ informations.description }}</p>
  <p>Outils utilises: {{ informations.stack }}</p>
    <p>Status: {{ informations.health }}</p>
	<p>Version: {{ informations.version }}</p>
	<p>Build: {{ informations.build }}</p>

  </div>
</template> -->
<template>
  <div class="container">
    <div class="info">
      <p><strong>{{ informations.name }} :</strong> {{ informations.description }}</p>
      <p>
        <strong>Health :</strong>  {{ informations.health }}</p>
      <p>
         <strong>Version: </strong>{{ informations.version }}
          <strong>Build:</strong> {{ informations.build }}</p>
    </div>

    <table class="stack">
      <thead>
        <tr>Stack utilisés</tr>
        <tr>
          <th>Nom</th>
          <th>Version</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(version, name) in informations.stack" :key="name">
          <td>{{ name }}</td>
          <td >{{ version }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>


<script>
import axios from 'axios';

export default {
  data() {
    return {
      informations: {},
    };
  },
  methods: {
    getHealthCheck() {
      const path = 'http://localhost:3000/up';
      axios.get(path)
        .then((res) => {
          this.informations = res.data;
        })
        .catch((error) => {
          // eslint-disable-next-line
          console.error(error);
        });
    },
  },
  created() {
    this.getHealthCheck();
  },
};
</script>
