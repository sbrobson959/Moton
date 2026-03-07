<script>
	import FAQItem from '../../lib/components/FAQItem.svelte';
	const FAQS = [
		{
			question: 'What is planned for the Moton Site?',
			answer:
				'The development plan prioritizes new housing, supplemented by small neighborhood shops and limited community space. It is designed as a residential-focused project rather than a large commercial enterprise, aiming to provide homes alongside essential everyday services like local food options and neighborhood businesses.'
		},
		{
			question: 'How large is the site?',
			answer:
				'The Moton Site encompasses 3.5 acres, located at the intersection of Pine Street and Greenwood Avenue.'
		},
		{
			question: 'Will this raise rents or property taxes?',
			answer:
				'No, the plan is specifically designed to reduce housing cost pressures rather than increase them. Given that many North Tulsa residents are already facing high housing costs, the project utilizes public funding to support both housing and retail development, ensuring affordability is maintained.'
		},
		{
			question: 'Is this development meant for current residents or new people moving in?',
			answer:
				'The development is intended for both groups. The project aims to serve people already living in North Tulsa, former residents looking to return, families seeking attainable homeownership, single professionals, and seniors requiring housing.'
		},
		{
			question: 'Will there be homes that are actually affordable?',
			answer:
				'Affordability is a central focus of the project. Because it is a significant challenge, the development leverages available public funding to ensure that homeownership at this site is truly attainable for residents.'
		},
		{
			question: 'Will there be opportunities to own—not just rent?',
			answer:
				'Yes, the strongest recommendation for the site is to create ownership-friendly housing. The plan explicitly prioritizes opportunities for residents to purchase homes rather than just renting.'
		},
		{
			question: "Are we just being 'studied again,' or will something actually happen?",
			answer:
				'The primary goal is action, not further reports. PartnerTulsa aims to see visible progress within approximately 18 months, beginning with infrastructure improvements and early construction so the community can witness tangible movement.'
		},
		{
			question: 'What kind of stores or businesses could be on the site?',
			answer:
				"The site could feature food options, neighborhood services, and small local businesses rather than big chains or a nightlife district. These choices are intended to leverage North Tulsa's existing spending power and ensure that money stays within the community."
		},
		{
			question: 'How will the history of Moton Hospital and Greenwood be respected?',
			answer:
				"The site's rich history is viewed as a strength to be celebrated, not erased. The design will incorporate cultural storytelling, provide visible acknowledgment of the site's legacy, and include community-centered programming to honor the past."
		},
		{
			question:
				'Will local workers, builders, and businesses be part of this—or will outsiders get everything?',
			answer:
				'Yes, local participation is central to the project. The plan prioritizes hiring local contractors where possible, supporting small builders, and forming partnerships that build local capacity rather than replacing it with outside entities.'
		},
		{
			question: 'How will residents stay informed and have a say as this moves forward?',
			answer:
				'Partner Tulsa and the Terence Crutcher Foundation are committed to transparency and community engagement. They will provide regular public updates, establish clear timelines, track and share progress openly, and create a Community Advisor Board to ensure residents have a voice.'
		}
	];
</script>

<div class="mx-auto max-w-3xl">
	<h2 class="font-graebenbach my-5 text-4xl font-bold">Frequently Asked Questions</h2>

	{#each FAQS as { question, answer }}
		<FAQItem {question} {answer} />
	{/each}
</div>
