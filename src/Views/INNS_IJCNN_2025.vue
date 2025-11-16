<script setup>
	import KeyDates from '@/components/INNS_IJCNN_2025/KeyDates.vue';
	import IntroSection from '@/components/INNS_IJCNN_2025/IntroSection.vue';
	import MeetTheOrganizers from '@/components/INNS_IJCNN_2025/MeetTheOrganizers.vue';
	import SpecialSponsoredMeeting from '@/components/INNS_IJCNN_2025/SpecialSponsoredMeeting.vue';
	import MoreInfo from '@/components/INNS_IJCNN_2025/MoreInfo.vue';
	import HeaderSection from '@/components/INNS_IJCNN_2025/HeaderSection.vue';
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
