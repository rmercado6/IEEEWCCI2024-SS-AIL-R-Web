<script setup>

import KeyDates from "@/components/IEEE_WCCI_2024/KeyDates.vue";
import IntroSection from "@/components/IEEE_WCCI_2024/IntroSection.vue";
import MeetTheOrganizers from "@/components/IEEE_WCCI_2024/MeetTheOrganizers.vue";
import SpecialSponsoredMeeting from "@/components/IEEE_WCCI_2024/SpecialSponsoredMeeting.vue";
import MoreInfo from "@/components/IEEE_WCCI_2024/MoreInfo.vue";
import HeaderSection from "@/components/IEEE_WCCI_2024/HeaderSection.vue";
</script>

<template>
    <header>
        <HeaderSection/>
    </header>

    <main>
        <IntroSection/>
        <KeyDates/>
        <MoreInfo/>
        <MeetTheOrganizers/>
        <SpecialSponsoredMeeting/>
    </main>
</template>

<style scoped>

</style>