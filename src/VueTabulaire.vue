<script>
import axios from 'axios';

export default {
  data() {
    return {
      students: {},
      loading : false,
    };
  },
  methods: {
    async getStudents() {
      this.loading = true;
      try {
      const resp = await axios.get('http://localhost:3000/students/api');
      this.students = resp.data;
    }

      catch(err){
          // eslint-disable-next-line
          this.loading = false;
          console.error(err);
        }finally{
          this.loading = false;
        };
    },
  },
  created() {
    this.getStudents();
  },
};
</script>


<template>
  <div v-if="loading">Chargement de donnees...</div>
  <table>
  <thead>
    <tr>
      <th>Nom</th>
      <th>Prénom</th>
      <th>Actions</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="students in students" :key="students.createdAt">
      <td>{{ students.name }}</td>
      <td>{{ students.prenom }}</td>
      <td>
        <button class="edit">editer</button>
        <button class="delete">delete</button>
      </td>
    </tr>
  </tbody>
</table>

</template>

<style scoped></style>
