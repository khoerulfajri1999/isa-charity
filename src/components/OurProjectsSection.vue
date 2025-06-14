<template>
    <section class="our-projects">
        <div class="container wrapper-content">
            <h1>Our projects</h1>
            <p>are very different in terms of priority, scale and complexity of implementation</p>
        
            <div class="project-item black" ref="firstProject">
                <div class="project-item-inner">
                    <h2>Emergency Aid. WAR 2022.</h2>
                    <p>providing food and medicine to the shelters and animals which lost their homes and families due to the war</p>
                </div>
            </div>
        
            <div class="project-item green" ref="secondProject">
                <div class="project-item-inner">
                    <h2>Non-commercial feed line</h2>
                    <p>construction of industrial production base where food for shelters will be produced on a free basis</p>
                </div>
            </div>
        
            <div class="project-item pink" ref="thirdProject">
                <div class="project-item-inner">
                    <h2>Education and Control</h2>
                    <p>lectures on communication, organisation and coordination of processes, control over the use of aid</p>
                </div>
            </div>
        </div>
    </section>
  </template>
  
  <script>
  import gsap from "gsap";
  import { ScrollTrigger } from "gsap/ScrollTrigger";

  gsap.registerPlugin(ScrollTrigger);

  export default {
    name: "OurProjectsSection",
    mounted() {
     gsap.fromTo(
      this.$refs.firstProject,
      { opacity: 0, x: -100 },
      {
        opacity: 1,
        x: 0,
        duration: 1,
        scrollTrigger: {
          trigger: this.$refs.firstProject,
          start: "top 100%",
          toggleActions: "play none none reset",
        },
      }
     );
     gsap.fromTo(
      this.$refs.firstProject,
      { opacity: 1, x: 0 },
      {
        opacity: 0,
        x: -100,
        duration: 1,
        scrollTrigger: {
          trigger: this.$refs.firstProject,
          start: "bottom top",
          toggleActions: "play none none reverse",
        },
      }
     );
     gsap.fromTo(
      this.$refs.secondProject,
      { opacity: 0, x: -100 },
      {
        opacity: 1,
        x: 0,
        duration: 1,
        scrollTrigger: {
          trigger: this.$refs.secondProject,
          start: "top 100%",
          toggleActions: "play none none reset",
        },
      }
     );
     gsap.fromTo(
      this.$refs.secondProject,
      { opacity: 1, x: 0 },
      {
        opacity: 0,
        x: -100,
        duration: 1,
        scrollTrigger: {
          trigger: this.$refs.secondProject,
          start: "bottom top",
          toggleActions: "play none none reverse",
        },
      }
     );
     gsap.fromTo(
      this.$refs.thirdProject,
      { opacity: 0, x: -100 },
      {
        opacity: 1,
        x: 0,
        duration: 1,
        scrollTrigger: {
          trigger: this.$refs.thirdProject,
          start: "top 100%",
          toggleActions: "play none none reset",
        },
      }
     );
     gsap.fromTo(
      this.$refs.thirdProject,
      { opacity: 1, x: 0 },
      {
        opacity: 0,
        x: -100,
        duration: 1,
        scrollTrigger: {
          trigger: this.$refs.thirdProject,
          start: "bottom top",
          toggleActions: "play none none reverse",
        },
      }
     );
    },
  }
  </script>

<style lang="sass" scoped>
@import "@/assets/styles/OurProjectsStyle.sass";

</style>