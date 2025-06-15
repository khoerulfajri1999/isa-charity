<template>
    <!-- Tombol kanan atas -->
    <a
      href="#"
      aria-label="Donasi"
      class="donate-button">
      <span>donate</span>
    </a>

    <!-- Logo kanan bawah -->
    <a
      href="#"
      aria-label="Logo Bottom Right"
      class="logo-bottom-right">
      <img src="../assets/images/logo1.svg" alt="Logo Bottom Right">
      <img src="../assets/images/logo2.svg" alt="Logo Bottom Right">
    </a>
    <HeroSection />
    <AboutSection />
    <OurProjectsSection />
    <HelpSection />
    <OurTeamSection />
    <CitizenSection />
    <OurPartnersSection />
    <ContactSection />
</template>
  
<script>
    import AboutSection from '@/components/AboutSection.vue';
    import CitizenSection from '@/components/CitizenSection.vue';
    import ContactSection from '@/components/ContactSection.vue';
    import HelpSection from '@/components/HelpSection.vue';
    import HeroSection from '@/components/HeroSection.vue'
    import OurPartnersSection from '@/components/OurPartnersSection.vue';
    import OurProjectsSection from '@/components/OurProjectsSection.vue';
    import OurTeamSection from '@/components/OurTeamSection.vue';

    export default {
        components: { 
            HeroSection,
            AboutSection,
            OurProjectsSection,
            HelpSection,
            OurTeamSection,
            CitizenSection,
            OurPartnersSection,
            ContactSection
        },
    }
</script>
<style lang="sass" scoped>
@import "@/assets/styles/LandingPageStyle.sass";

</style>
  