<template>
    <HeroSection />
    <AboutSection />
    <OurProjectsSection />
    <HelpSection />
    <OurTeamSection />
</template>
  
<script>
    import AboutSection from '@/components/AboutSection.vue';
    import HelpSection from '@/components/HelpSection.vue';
    import HeroSection from '@/components/HeroSection.vue'
    import OurProjectsSection from '@/components/OurProjectsSection.vue';
    import OurTeamSection from '@/components/OurTeamSection.vue';

    export default {
        components: { 
            HeroSection,
            AboutSection,
            OurProjectsSection,
            HelpSection,
            OurTeamSection
        },
    }
</script>
  