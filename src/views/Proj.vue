<template>
  <div>
    <div v-if="mySkills" class="divi bg-dark row p-1">
      <h1>My Skills</h1>
      <h5>Programming Languages</h5>
      <mySkillsComp
        v-for="mySkill in mySkills"
        :key="mySkill.id"
        :mySkill="mySkill"
      />
    </div>
    <div v-else>Processing...</div>
  </div>
</template>

<script>
import mySkillsComp from "@/components/Proj-Comp.vue";

export default {
  data() {

    return {
      
      mySkills: null,
    };
  },
  mounted() {
    this.fetchMySkills();
  },
  methods: {
    async fetchMySkills() {
      try {
        const response = await fetch("https://avsidwell.github.io/data.json");
        const data = await response.json();
        this.mySkills = data.mySkills;
      } catch (error) {
        console.error("Error fetching data:", error);
      }
    },
  },
  components: { mySkillsComp },
};
</script>

<style>
.divi {
  margin: auto;
  width: 100vw;
}

h1 {
  color: #cbe4de;
}
</style>
