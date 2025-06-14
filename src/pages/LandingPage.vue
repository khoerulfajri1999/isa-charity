<template>
    <HeroSection />
    <AboutSection />
</template>
  
<script>
    import AboutSection from '@/components/AboutSection.vue';
    import HeroSection from '@/components/HeroSection.vue'

    export default {
        components: { 
            HeroSection,
            AboutSection 
        },
    }
</script>
  