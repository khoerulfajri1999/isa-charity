<template>
    <HeroSection />
    <AboutSection />
    <OurProjectsSection />
</template>
  
<script>
    import AboutSection from '@/components/AboutSection.vue';
    import HeroSection from '@/components/HeroSection.vue'
    import OurProjectsSection from '@/components/OurProjectsSection.vue';

    export default {
        components: { 
            HeroSection,
            AboutSection,
            OurProjectsSection
        },
    }
</script>
  