<template>
  <div class="student-show">
    <h1>{{ student.first_name }} {{ student.last_name }}</h1>
    <img v-bind:src="`${student.photo_url}`" alt="" />
    <!-- <h2>{{ student.experiences[0] }}</h2> -->
    <h3>Contact Information</h3>
    <p>
      <strong>Email:</strong>
      {{ student.email }} |
      <strong>phone number:</strong>
      {{ student.phone_number }} |
      <strong>bio:</strong>
      {{ student.short_bio }}
    </p>
    <strong>linkedIn:</strong>
    {{ student.linkedin_url }}
    <strong>Twitter:</strong>
    {{ student.twitter_handle }} |
    <strong>Website:</strong>
    {{ student.personal_website }} |
    <strong>Resume:</strong>
    {{ student.online_resume_url }} |
    <strong>Resume:</strong>
    {{ student.online_resume_url }} |
    <strong>Github:</strong>
    {{ student.github_url }}
    <br />
    <h3>Experiences</h3>
    <div v-for="experience in student.experiences">
      <p>{{ experience.start_date }} - {{ experience.end_date }}</p>
      <p>
        <strong>job title:</strong>
        {{ experience.job_title }} @ {{ experience.company_name }}
      </p>
      <p>
        <strong>details:</strong>
        {{ experience.details }}
      </p>
    </div>
    <h2>Education</h2>
    <div v-for="school in student.education">
      <h3>{{ school.university_name }}</h3>
      <h5>{{ school.degree }}</h5>
      <h6>From: {{ school.start_date }} To: {{ school.end_date }}</h6>
      <p>{{ school.details }}</p>
    </div>
    <h2>Skills</h2>
    <div v-for="skill in student.skills">
      <h3>{{ skill.skill_name }}</h3>
    </div>
    <h2>Capstones</h2>
    <div v-for="capstone in student.capstones">
      <h3>{{ capstone.name }}</h3>
      <img v-bind:src="`${capstone.screenshot_url}`" v-bind:alt="`${capstone.name}`" />
      <h4>{{ capstone.description }}</h4>
      <router-link to="/">Back to all students</router-link>
    </div>
  </div>
</template>

<style>
img {
  height: 250px;
}
</style>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      student: {},
    };
  },
  created: function() {
    axios.get("/api/students/" + this.$route.params.id).then(response => {
      console.log("student show", response);
      this.student = response.data;
    });
  },
  methods: {},
};
</script>
