<template>
    <section class="hero" ref="hero">
      <div class="wrap-content container">
        <div class="hero-image" ref="heroImage">
          <img :src="currentImage" alt="hero image" />
        </div>        
        <h1 ref="heroTitle">Innovative Solutions for Animals</h1>
      </div>
      
      <p ref="heroParagraph">charity organization</p>
  
      <div ref="socialIcons" class="social-icons">
        <a href="#" aria-label="YouTube"><img src="../assets/images/hero/icon-youtube.svg" alt="YouTube"/></a>
        <a href="#" aria-label="Instagram"><img src="../assets/images/hero/icon-instagram.svg" alt="Instagram"/></a>
        <a href="#" aria-label="Facebook"><img src="../assets/images/hero/icon-facebook.svg" alt="Facebook"/></a>
        <a href="#" aria-label="Patreon"><img src="../assets/images/hero/icon-patreon.svg" alt="Patreon"/></a>
        <a href="#" aria-label="Telegram"><img src="../assets/images/hero/icon-telegram.svg" alt="Telegram"/></a>
      </div>
  
      <div ref="arrow" class="arrow">^</div>
    </section>
  </template>
  
  <script>
  import gsap from "gsap";
  
  export default {
      name: "HeroSection",
      data() {
        return {
          images: [
            require('../assets/images/hero/hero1.svg'),
            require('../assets/images/hero/hero2.svg')
          ],
          currentIndex: 0,
          intervalId: null,
          hasAnimated: false,
        };
      },
      computed: {
        currentImage() {
          return this.images[this.currentIndex];
        },
      },
      mounted() {
        // IntersectionObserver untuk mendeteksi saat section tampil
        const options = {
          root: null,
          rootMargin: "0px",
          threshold: 0.5,
        };
        this.observer = new IntersectionObserver((entries) => {
          entries.forEach((entry) => {
            if (entry.isIntersecting && !this.hasAnimated) {
              this.animateHero();
              this.hasAnimated = true;
            }
          });
        }, options);
  
        this.observer.observe(this.$refs.hero);
      },
      beforeUnmount() {
        clearInterval(this.intervalId);
        if(this.observer) {
          this.observer.disconnect();
        }
      },
      methods: {
        animateHero() {
          gsap.from(this.$refs.heroImage, {
            y: -100,
           opacity: 0,
            duration: 2,
            ease: "power4.out",
          });
  
          gsap.from(this.$refs.heroTitle, {
            x: 100,
           opacity: 0,
            duration: 2,
            ease: "power4.out",
          });
  
          gsap.from(this.$refs.heroParagraph, {
            y: 100,
           opacity: 0,
            duration: 2,
            ease: "power4.out",
          });
  
          gsap.from(this.$refs.socialIcons, {
            y: 100,
           opacity: 0,
            duration: 2,
            ease: "power4.out",
          });
  
          gsap.from(this.$refs.heroBtn, {
            y: 100,
           opacity: 0,
            duration: 2,
            ease: "power4.out",
          });
  
          // Animasi arrow naik turun
          gsap.to(this.$refs.arrow, {
            y: -10,
            scale: 0.1,
            duration: 2,
            repeat: -1,
            yoyo: true,
            ease: "power1.inOut",
          });
  
          this.startSlideshow();
        },
        startSlideshow() {
          this.intervalId = setInterval(this.nextImage, 3000);
        },
        nextImage() {
          gsap.to(this.$refs.heroImage, {
              duration: 0.2,
              y: 400,
            opacity: 0,
              ease: "power.inOut",
              onComplete: () => {
                this.currentIndex = (this.currentIndex + 1) % this.images.length;
  
                gsap.set(this.$refs.heroImage, { y: -400,opacity: 0 });
  
                gsap.to(this.$refs.heroImage, {
                  duration: 0.2,
                  y: 0,
                opacity: 1,
                  ease: "power.inOut",
                });
              },
          });
        },
      },
    };
  </script>
  
  <style lang="sass" scoped>
  @import "@/assets/styles/HeroStyle.sass";
  
  </style>
  