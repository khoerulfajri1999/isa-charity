<template>
    <section class="our-partners container">
      <h1>Our partners</h1>
      <p>are take care of our fund and help us with many questions</p>
  
      <div class="grid">
        <div v-for="(item, index) in partners" :key="index" class="grid-item" ref="gridItems">
          <img :src="item.image" :alt="item.name" />
        </div>
      </div>
    </section>
  </template>
  
  <script>
  import gsap from "gsap";
  import { ScrollTrigger } from "gsap/ScrollTrigger";

  gsap.registerPlugin(ScrollTrigger);

  export default {
    name: "OurPartners",
    data() {
      return {
        partners: [
          { name: "Advires", image: require("../assets/images/partner/partner1.jpg") },
          { name: "OvidWind", image: require("../assets/images/partner/partner2.png") },
          { name: "TBS Industry", image: require("../assets/images/partner/partner3.png") },
          { name: "Accurl", image: require("../assets/images/partner/partner4.png") },
          { name: "Laudis", image: require("../assets/images/partner/partner5.png") },
          { name: "KickBite", image: require("../assets/images/partner/partner6.jpeg") },
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
  };
  
  </script>

<style lang="sass" scoped>
@import "@/assets/styles/OurPartnersStyle.sass";

</style>