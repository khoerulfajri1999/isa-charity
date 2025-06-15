<template>
  <section class="contact-us">
    <div class="contact-info container">
      <div class="contact-content">
        <h1>Contact us</h1>
        <p>Kyiv, Ukraine</p>
        <p>mail@isa.co.ua</p>

        <div ref="socialIcons" class="social-icons">
          <a href="#" aria-label="YouTube"><img src="../assets/images/hero/icon-youtube.svg" alt="YouTube"/></a>
          <a href="#" aria-label="Instagram"><img src="../assets/images/hero/icon-instagram.svg" alt="Instagram"/></a>
          <a href="#" aria-label="Facebook"><img src="../assets/images/hero/icon-facebook.svg" alt="Facebook"/></a>
          <a href="#" aria-label="Patreon"><img src="../assets/images/hero/icon-patreon.svg" alt="Patreon"/></a>
          <a href="#" aria-label="Telegram"><img src="../assets/images/hero/icon-telegram.svg" alt="Telegram"/></a>
        </div>
      </div>

      <div class="contact-image" ref="contactImage">
        <img src="../assets/images/hero/cat-illustration.svg" alt="Cat illustration" />
      </div>
    </div>
  </section>
</template>

<script>
import gsap from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

export default {
  name: "ContactUs",
  mounted() {
     gsap.fromTo(
      this.$refs.contactImage,
      { opacity: 1, y: 100 },
      {
        opacity: 1,
        y: 0,
        duration: 1,
        scrollTrigger: {
          trigger: this.$refs.contactImage,
          start: "top 100%",
          toggleActions: "play none none reset",
        },
      }
     );
     gsap.fromTo(
      this.$refs.contactImage,
      { opacity: 1, y: 0 },
      {
        opacity: 1,
        y: 100,
        duration: 1,
        scrollTrigger: {
          trigger: this.$refs.contactImage,
          start: "bottom top",
          toggleActions: "play none none reverse",
        },
      }
     );
    },
}
</script>

<style lang="sass" scoped>
@import "@/assets/styles/ContactStyle.sass";

</style>
