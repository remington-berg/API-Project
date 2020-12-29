<template>
  <div class="home">
    <div v-for="student in students">
      <div class="card mb-3" style="max-width: 540px;">
        <div class="row g-0">
          <div class="col-md-4">
            <router-link v-bind:to="`/student/${student.id}`">
              <img v-bind:src="`${student.photo_url}`" v-bind:alt="`${student.last_name}`" />
            </router-link>
          </div>
          <div class="col-md-8">
            <div class="card-body">
              <h5 class="card-title">Card title</h5>
              <p class="card-text">
                This is a wider card with supporting text below as a natural lead-in to additional content. This content
                is a little bit longer.
              </p>
              <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
            </div>
          </div>
        </div>
      </div>

      <h1>{{ student.first_name }} {{ student.last_name }}</h1>

      <!-- <p>{{ student.skills[0].skill_name }}</p> -->
    </div>
  </div>
</template>

<style>
.card mb-3 {
  /* text-align: center; */
  display: block;
  margin-left: auto;
  margin-right: auto;
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
