<script setup>
import HeaderSection from './components/HeaderSection.vue'
import IntroSection from './components/IntroSection.vue'
import KeyDates from './components/KeyDates.vue'
import MoreInfo from './components/MoreInfo.vue'
import MeetTheOrganizers from './components/MeetTheOrganizers.vue'
import SpecialSponsoredMeeting from './components/SpecialSponsoredMeeting.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <header>
    <HeaderSection />
  </header>

  <main>
    <IntroSection />
    <KeyDates />
    <MoreInfo />
    <MeetTheOrganizers />
    <SpecialSponsoredMeeting />
  </main>

  <footer>
    <Footer />
  </footer>
</template>

<style scoped>
</style>
