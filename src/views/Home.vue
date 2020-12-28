<template>
  <div class="home">
    <div v-for="student in students">
      <h1>{{ student.first_name }} {{student.last_name }}</h1>
      <img v-bind:src="`${student.photo_url}`" v-bind:alt="`${student.last_name}`">
    </div>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      students: [{first_name: "bob", last_name: "smith"}],
    };
  },
  created: function() {
    this.indexStudents();
  },
  methods: {
    indexStudents: function() {
      axios.get("/api/students").then(response => {
        console.log("students index", response); this.students = response.data;
      });
    },
  },
};
</script>
