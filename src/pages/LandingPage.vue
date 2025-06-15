<template>
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
  