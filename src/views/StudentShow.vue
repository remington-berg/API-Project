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
    <h1>{{ student.first_name }}{{ student.last_name }}</h1>
    <h2>{{ student.experiences[0].job_title }}</h2>
    <h2>Education</h2>
    <div v-for="school in student.education">
      <h3>{{ school.university_name }}</h3>
      <h5>{{ school.degree }}</h5>
      <h6>From: {{school.start_date}} To: {{ school.end_date }}</h6>
      <p>{{ school.details }}</p>
    </div>
    <h2>Skills</h2>
    <div v-for="skill in student.skills">
      <h3>{{ skill.skill_name }}</h3>
    </div>
    <h2>Capstones</h2>
    <div v-for="capstone in student.capstones">
      <h3>{{ capstone.name }}</h3>
      <img v-bind:src="`${capstone.screenshot_url}`" v-bind:alt="`${capstone.name}`">
      <h4>{{ capstone.url }}</h4>
      <h4>{{ capstone.description }}</h4>
    </div>
    <a class="twitter-timeline" href="https://twitter.com/TwitterDev?ref_src=twsrc%5Etfw">Tweets by TwitterDev</a>
    <router-link to="/">Back to all students</router-link>
  </div>
</template>


<style>
  img {
    height: 250px;
  }
</style>

<script>
export default {
  data: function() {
    return {
      student:
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
             degree: "Computer Science",              university_name: "MIT",
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
    };
  }
};
</script>
