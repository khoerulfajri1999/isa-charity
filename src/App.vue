<template>
  <LandingPage />
</template>

  <script>
  import LandingPage from '@/pages/LandingPage.vue'
  
  export default {
    components: { LandingPage },
  }
  </script>

<style>
  body {
    margin: 0;
    padding: 0;
    font-family: 'DM Sans', sans-serif;
    overflow-y: scroll; 
  }
  .container {
  max-width: 80vw;
  margin: 0 auto;
  padding: 20px;
}
</style>
