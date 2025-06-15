<template>
    <section class="citizen-grid">
        <div class="container">
            <h1>Socially active citizens</h1>
            <p>support us</p>
        
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
            { name: "Oleksiy Tritenko", profession:"theater and film actress", image: require('../assets/images/citizen/citizen1.jpg') },
            { name: "Stanislav Boklan", profession:"People's Artist of Ukraine", image: require('../assets/images/citizen/citizen2.jpg') },
            { name: "Alexander Rudinsky", profession:"theater and film actor", image: require('../assets/images/citizen/citizen3.jpg') },
            { name: "Oksana Zhdanova", profession:"theater and film actress", image: require('../assets/images/citizen/citizen4.jpg') },
            { name: "Natalka Denisenko", profession:"theater and film actress", image: require('../assets/images/citizen/citizen5.jpg') },
            { name: "Maksym Samchyk", profession:"theater and film actor", image: require('../assets/images/citizen/citizen6.jpg') },
            { name: "Kateryna Vyshneva", profession:"theater and film actress", image: require('../assets/images/citizen/citizen7.jpg') },
            { name: "Irma Vitovska", profession:"Honored Actress of Ukraine", image: require('../assets/images/citizen/citizen8.jpg') },
            { name: "Igor Portyanko", profession:"actor of theater and cinema", image: require('../assets/images/citizen/citizen9.jpg') },
            { name: "Dmytro Surzhikov", profession:"Honored Artist of Ukraine", image: require('../assets/images/citizen/citizen10.jpg') },
            { name: "Daria Barihashvili", profession:"theater and film actress", image: require('../assets/images/citizen/citizen11.jpg') },
            { name: "Vera Kobzar", profession:"theater and film actress", image: require('../assets/images/citizen/citizen12.jpg') },
            { name: "Andriy Fedynchyk", profession:"theater and film actor", image: require('../assets/images/citizen/citizen13.jpg') },
            { name: "Anastasia Nesterenko", profession:"theater and film actress", image: require('../assets/images/citizen/citizen14.jpg') },
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
@import "@/assets/styles/CitizenStyle.sass";

</style>