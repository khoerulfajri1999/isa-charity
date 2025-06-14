<template>
    <section class="about container" ref="about">
      <h1>We are</h1>
      <p>team of like-minded people, socially active companies, media personalities, volunteers who help low-income shelters and foster carers to support homeless animals.</p>
  
      <h1>Our primary goal</h1>
      <p>is to provide animals with the most necessary things - food, medicine, and urgent needs for the livelihood of shelters. We believe in our power and the power of conscious citizens who care about the environment and their health, who understand the importance of helping each other, especially our little friends. Growth begins with your care for your loved ones. Animals are one of the closest creatures to humans who remain with us throughout our lives. We all know the healing power of warmth, grace, and big loving eyes.</p>
  
      <blockquote>“Animals need to have friends. Just like humans.” <br>- James Herriot, All Creatures Great and Small</blockquote>
  
      <p>Who else if not we should support our younger brothers, especially in difficult times? Let's be friends!</p>
  
      <div class="video" ref="aboutVideo">
        <iframe src="https://www.youtube.com/embed/5Wk1rp99B7o?si=fViu04d8IEfJ5U3r" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
      </div>
    </section>
  </template>
  
  <script>
  import gsap from "gsap";
  import { ScrollTrigger } from "gsap/ScrollTrigger";

  gsap.registerPlugin(ScrollTrigger);
  
  export default {
    name: "AboutSection",
    mounted() {
     gsap.fromTo(
      this.$refs.aboutVideo,
      { opacity: 0, y: 100 },
      {
        opacity: 1,
        y: 0,
        duration: 1,
        scrollTrigger: {
          trigger: this.$refs.aboutVideo,
          start: "top 100%",
          toggleActions: "play none none reset",
        },
      }
     );
     gsap.fromTo(
      this.$refs.aboutVideo,
      { opacity: 1, y: 0 },
      {
        opacity: 0,
        y: 100,
        duration: 1,
        scrollTrigger: {
          trigger: this.$refs.aboutVideo,
          start: "bottom top",
          toggleActions: "play none none reverse",
        },
      }
     );
    },
  };
  </script>
  
  <style lang="sass" scoped>
  @import "@/assets/styles/AboutStyle.sass";
  </style>