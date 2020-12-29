<template>
  <div class="home">
    <div v-for="student in students">
      <h1>{{ student.first_name }} {{student.last_name }}</h1>
      <router-link v-bind:to="`/student/${student.id}`">
      <img v-bind:src="`${student.photo_url}`" v-bind:alt="`${student.last_name}`">
      </router-link>
      <p>{{ student.skills[0].skill_name }}</p>
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
      students: [
        {
          id: 1,
          first_name: "bob",
          last_name: "smith",
          email: "b@example.com",
          password_digest: "aslkjdfaslkdjfh",
          phone_number: "555-555-5555",
          short_bio: "a;sdf;lasdjhnklajsdhg;salc",
          linkedin_url: "linkedin.com",
          twitter_handle: "@xyz",
          personal_website: "bob.com",
          online_resume_url: "bob.com/resume",
          github_url: "github.com/bob",
          photo_url: "https://i.imgur.com/SbijEKc.jpg",
          experiences: [
            {
              id: 1,
              student_id: 1,
              start_date: "12/8/2020",
              end_date: "present",
              job_title: "Web Developer",
              company_name: "Google",
              details: "Google Web Developer"
            },
          ],
          education: [
            {
              id: 1,
              student_id: 1,
              start_date: "12/8/2016",
              end_date: "12/8/2020",
              degree: "Computer Science",
              university_name: "MIT",
              details: "bob is smart"
            },
          ],
          skills: [
            {
              id: 1,
              student_id: 1,
              skill_name: "smithing",
            }
          ],
          capstones: [
            {
              id: 1,
              student_id: 1,
              name: "WebSmithing",
              description: "Website about smithing",
              url: "websmithing.com",
              screenshot_url: "https://upload.wikimedia.org/wikipedia/commons/f/f9/Kov%C3%A1%C5%99_p%C5%99i_pr%C3%A1ci_%28Velikono%C4%8Dn%C3%AD_trhy_na_V%C3%A1clavsk%C3%A9m_n%C3%A1m%C4%9Bst%C3%AD%29_055.jpg"
            },
          ],
        },
      ],
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
