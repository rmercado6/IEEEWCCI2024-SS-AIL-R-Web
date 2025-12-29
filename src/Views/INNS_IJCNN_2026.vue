<script setup>
	import KeyDates from '@/components/INNS_IJCNN_2026/KeyDates.vue';
	import IntroSection from '@/components/INNS_IJCNN_2026/IntroSection.vue';
	import MeetTheOrganizers from '@/components/INNS_IJCNN_2026/MeetTheOrganizers.vue';
	import MoreInfo from '@/components/INNS_IJCNN_2026/MoreInfo.vue';
	import HeaderSection from '@/components/INNS_IJCNN_2026/HeaderSection.vue';
	import SpecialSponsoredMeeting from '@/components/INNS_IJCNN_2026/SpecialSponsoredMeeting.vue';
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
</template>
