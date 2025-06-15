<template>
    <section class="help-grid">
        <div class="container">
            <h1>We want to help</h1>
            <p>homeless packs, volunteers, guardians, overstayers, shelters and other organisations</p>
        
            <div class="grid">
              <div
                v-for="(item, index) in cards"
                :key="index"
                class="grid-item"
                ref="gridItems">
                  <div class="grid-inner">
                    {{ item }}
                  </div>
              </div>
            </div>
            <div class="apply" ref="applyRef">
              <h2>apply for help</h2>
              <a class="arrow"><img src="../assets/images/help/arrow.png" alt="arrow"/></a>
            </div>
        </div>
    </section>
  </template>
  
  <script>
  import gsap from "gsap";
  import { ScrollTrigger } from "gsap/ScrollTrigger";

  gsap.registerPlugin(ScrollTrigger);

  export default {
    name: "HelpSection",
    data() {
      return {
        cards: [
          "Shelter of Victoria Bulbyna",
          "City of faithful hearts",
          "Shelter of Natalia Tymoshenko",
          "Shelter of Jeanne Sass",
          "Shelter of Victoria Bondarenko",
          "Sterilization center",
          "Zoo chance",
          "Save lives",
          "City Center for the Treatment of Animals",
          "Society for the Protection of Animals in Sumy",
          "The right to life",
          "4 paws",
          "The kingdom of cats",
          "Zvir",
          "Mercy",
          "Happy dog",
          "Give me a paw, friend",
          "Friend",
          "Hope",
          "We are for the right to life",
          "Planeta",
          "Second Life",
          "Happy shore",
          "Retrieverteam",
          "Shelter of Irina Dobrolyubova",
          "Matlida",
          "Life",
          "Second chance",
          "SOS",
          "Best friends"
        ],
      };
    },
    mounted() {
      this.$nextTick(() => {
        this.$refs.gridItems.forEach((item) => {
          gsap.fromTo(
            item,
            {opacity: 0, y: 100},
            {
            opacity: 1,
              y: 0,
              duration: 1,
              scrollTrigger: {
                trigger: item,
                start: "top 110%",
                toggleActions: "play none none reset",
              },
            }
          );

          gsap.fromTo(
            item,
            {opacity: 1, y: 0},
            {
            opacity: 0,
              y: 50,
              duration: 0.5,
              scrollTrigger: {
                trigger: item,
                start: "bottom top",
                toggleActions: "play none none reverse",
              },
            }
          );
        });
      });
      gsap.fromTo(
      this.$refs.applyRef,
      { opacity: 0, x: -100 },
      {
        opacity: 1,
        x: 0,
        duration: 1,
        scrollTrigger: {
          trigger: this.$refs.applyRef,
          start: "top 100%",
          toggleActions: "play none none reset",
        },
      }
     );
     gsap.fromTo(
      this.$refs.applyRef,
      { opacity: 1, x: 0 },
      {
        opacity: 0,
        x: -100,
        duration: 1,
        scrollTrigger: {
          trigger: this.$refs.applyRef,
          start: "bottom top",
          toggleActions: "play none none reverse",
        },
      }
     );
    },
  }
  </script>

<style lang="sass" scoped>
@import "@/assets/styles/HelpStyle.sass";

</style>