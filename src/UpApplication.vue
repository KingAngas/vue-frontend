<template>
  <div class="container">
    <p>{{ informations.name }}</p>
    <p>{{ informations.health }}</p>
	<p>{{ informations.version }}</p>
	<p>{{ informations.build }}</p>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Up',
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
