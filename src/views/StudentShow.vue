<template>
  <div class=“student-show”>
    <h1>{{ student.first_name }}{{ student.last_name }}</h1>
    <h2>{{ student.experiences[0] }}</h2>

    <router-link to=“/students”>Back to all students</router-link>
  </div>
</template>

<script>
export default {
  data: function(){
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
    }
  }
}
</script>