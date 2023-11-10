<template>
    <div>
      <div v-if="myTestimonials" class="bg-dark row p-4">
        <myTestimonialsComp
          v-for="testimonial in myTestimonials"
          :key="testimonial.id"
          :testimonial="testimonial"
        />
      </div>
      <div v-else>Processing...</div>
    </div>
  </template>
  
  <script>
  import myTestimonialsComp from "@/components/References.vue";
  
  export default {
    data() {
      return {
        myTestimonials: [
          {
            "id": 1,
            "name": " Okuhle Gxotiwe",
            "view": "Sidwell is great logical thinker , pays attention to detail and isn't afraid to take risks.",
            "status": "Classmate",
            "picture": "https://i.postimg.cc/prd9XVH0/C12-Okuhle-Gwotiwe-1.jpg"
          },
          {
            "id": 2,
            "name": "Waydin Jochem",
            "view": "Sidwell is a vibrant and charismatic individual, who oftentimes finds himself taking a lead role in team-based assignments. He expresses himself boldly and is always readily available to take on a new challenge",
            "status": "Classmate",
            "picture": "https://i.postimg.cc/nrRM5yN6/Waydin-Jochem-C12-C1-25-Apr23-2.jpg"
          },
          {
            "id": 3,
            "name": "Jamie-Lee Kinnear",
            "view": "Sidwell is a remarkable programmer and has an analytical approach to problem-solving. He is a hardworking individual and dedicated to his work. He is a great peer and a team player. He shows initiative and I believe he would be a valuable asset to any company that would be lucky to have him.",
            "status": "Assistant-Lecturer",
            "picture": "https://i.postimg.cc/4NbMTJdC/Jammie.jpg"
          },
          {
            "id": 4,
            "name": "Asiphe Ndimlana",
            "view": "As an IT professional, Sidwell embodies dedication and excellence. He never fails to exceed expectations and possesses a remarkable work ethic alongside unparalleled proficiency in technical matters.",
            "status": "Classmate",
            "picture": "https://i.postimg.cc/hjszBzHz/C12-Asiphe-Ndimlana-1.jpg"
          },
          {
            "id": 5,
            "name": "Xola Bangaza",
            "view": "Sidwell tackles things differently but works great with teams and does relay what he does and how to do it greatly so anyone can work with him perfectly.",
            "status": "Classmate",
            "picture": "https://i.postimg.cc/xCnJhyFV/C12-C1-Xola-Bangaza-2.jpg"
          }
        ],
      };
    },
    components: { myTestimonialsComp },
  };
  </script>
  
  <style>
  
  </style>
  