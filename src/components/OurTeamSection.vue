<template>
    <section class="team-grid">
        <div class="container">
            <h1>Our Team</h1>
            <p>consists of completely different people who are united by a common desire - to help</p>
        
            <div class="grid">
              <div
                v-for="(item, index) in cards"
                :key="index"
                class="grid-item"
                ref="gridItems">
                  <div class="grid-inner">
                    <img :src="item.image" :alt="item.name">
                    <p>{{ item.name }}</p>
                    <span>{{ item.profession }}</span>
                  </div>
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
    name: "OurTeamSection",
    data() {
      return {
        cards: [
            { name: "Daryna Deriy", profession:"Chairman of the Board", image: require('../assets/images/team/team1.jpg') },
            { name: "Polina Snisarenko-Kulchytska", profession:"Curator of the Foundation", image: require('../assets/images/team/team2.jpg') },
            { name: "Bohdan Kulchytsky", profession:"Executive Manager", image: require('../assets/images/team/team3.jpg') },
            { name: "Mykhaylo Deriy", profession:"Operation Manager", image: require('../assets/images/team/team4.jpg') },
            { name: "Ksenia Nikishina", profession:"Office manager", image: require('../assets/images/team/team5.jpg') },
            { name: "Anna Andriychuk", profession:"SMM-manager", image: require('../assets/images/team/team6.jpg') },
            { name: "Anastasia Kovalchuk", profession:"Director", image: require('../assets/images/team/team7.jpg') },
            { name: "Basil Gloo", profession:"Web Developer", image: require('../assets/images/team/team8.png') },
            { name: "Lina Yakobchuk", profession:"Designer", image: require('../assets/images/team/team9.jpg') },
            { name: "Anastasia Yevchenko", profession:"Translator", image: require('../assets/images/team/team10.jpg') },
            { name: "Office Manager", profession:"open vacancy", image: require('../assets/images/team/team11.svg') },
            { name: "SEO specialist", profession:"open Vacancy", image: require('../assets/images/team/team12.svg') },
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
                start: "top 100%",
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
              duration: 1,
              scrollTrigger: {
                trigger: item,
                start: "bottom top",
                toggleActions: "play none none reverse",
              },
            }
          );
        });
      });
    },
  }
  </script>

<style lang="sass" scoped>
@import "@/assets/styles/OurTeamStyle.sass";

</style>