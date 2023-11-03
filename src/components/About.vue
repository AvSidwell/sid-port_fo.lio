<template>
    <div class="modal">
      <h2>About Me</h2>
      <p>{{ aboutContent }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        aboutContent: '',
      };
    },
    created() {
      // Generate random content for the "About" modal
      this.aboutContent = this.generateRandomContent();
    },
    methods: {
      generateRandomContent() {
        // Generate random text content for the modal
        // You can use lorem ipsum generators or any other method to create sample content.
        return 'Lorem ipsum dolor sit amet, consectetur adipiscing elit...';
      },
    },
  };
  </script>
  
  <style scoped>
  /* Add your modal styles here */
  </style>
  