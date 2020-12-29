<template>
  <div class="home">
    <div v-for="student in students">
      <div class="cardmb-3" style="max-width: 750px;">
        <div class="row g-0">
          <div class="col-md-4">
            <router-link v-bind:to="`/student/${student.id}`">
              <img v-bind:src="`${student.photo_url}`" alt="...">
            </router-link>
          </div>
          <div class="col-md-8">
            <div class="card-body">
              <h5 class="card-title">{{student.first_name}} {{student.last_name}}</h5>
              <p class="card-text">{{ student.short_bio }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.cardmb-3 {
  /* text-align: center; */
  display: block;
  margin-left: auto;
  margin-right: auto;
  padding-bottom: 1em;
}
</style>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      students: [],
    };
  },
  created: function() {
    this.indexStudents();
  },
  methods: {
    indexStudents: function() {
      axios.get("/api/students").then(response => {
        console.log("students index", response);
        this.students = response.data;
      });
    },
  },
};
</script>
