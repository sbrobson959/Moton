<script>
	import PrioritiesChart from '$lib/components/PrioritiesChart.svelte';
	import LikertChart from '$lib/components/LikertChart.svelte';

	let votes = {
		'Strongly Disagree': 10,
		Disagree: 20,
		Neutral: 30,
		Agree: 45,
		'Strongly Agree': 55
	};

	let surveyResults = [
		{
			questionNumber: 1,
			questionText:
				'My neighborhood has well-maintained sidewalks that make it easy to walk around.',
			votes: {
				stronglyDisagree: 3,
				disagree: 9,
				neutral: 4,
				agree: 5,
				stronglyAgree: 1
			}
		},
		{
			questionNumber: 2,
			questionText: 'My neighborhood needs better street lighting.',
			votes: {
				stronglyDisagree: 0,
				disagree: 0,
				neutral: 4,
				agree: 9,
				stronglyAgree: 9
			}
		},
		{
			questionNumber: 3,
			questionText: 'I feel safe walking around my neighborhood after dark.',
			votes: {
				stronglyDisagree: 6,
				disagree: 7,
				neutral: 5,
				agree: 3,
				stronglyAgree: 1
			}
		},
		{
			questionNumber: 4,
			questionText: 'Children are safe walking around my neighborhood.',
			votes: {
				stronglyDisagree: 2,
				disagree: 6,
				neutral: 4,
				agree: 8,
				stronglyAgree: 2
			}
		},
		{
			questionNumber: 5,
			questionText: "My neighborhood's roads are well-maintained and safe.",
			votes: {
				stronglyDisagree: 4,
				disagree: 5,
				neutral: 8,
				agree: 5,
				stronglyAgree: 0
			}
		},
		{
			questionNumber: 6,
			questionText: 'People drive too fast in my neighborhood.',
			votes: {
				stronglyDisagree: 0,
				disagree: 4,
				neutral: 5,
				agree: 7,
				stronglyAgree: 5
			}
		},
		{
			questionNumber: 7,
			questionText:
				'When I need city services in my neighborhood, the city is responsive and helpful.',
			votes: {
				stronglyDisagree: 1,
				disagree: 4,
				neutral: 12,
				agree: 5,
				stronglyAgree: 0
			}
		},
		{
			questionNumber: 8,
			questionText: 'Stray animals are a problem in my neighborhood.',
			votes: {
				stronglyDisagree: 0,
				disagree: 3,
				neutral: 2,
				agree: 7,
				stronglyAgree: 9
			}
		},
		{
			questionNumber: 9,
			questionText: 'My neighborhood has plenty of green space for people to enjoy.',
			votes: {
				stronglyDisagree: 8,
				disagree: 4,
				neutral: 2,
				agree: 8,
				stronglyAgree: 0
			}
		},
		{
			questionNumber: 10,
			questionText: 'I can walk to find groceries and other essentials.',
			votes: {
				stronglyDisagree: 9,
				disagree: 5,
				neutral: 3,
				agree: 4,
				stronglyAgree: 1
			}
		},
		{
			questionNumber: 11,
			questionText: 'I need a car to navigate daily life.',
			votes: {
				stronglyDisagree: 1,
				disagree: 0,
				neutral: 1,
				agree: 10,
				stronglyAgree: 10
			}
		},
		{
			questionNumber: 12,
			questionText: 'Housing costs in my neighborhood are reasonable and fair.',
			votes: {
				stronglyDisagree: 0,
				disagree: 5,
				neutral: 12,
				agree: 4,
				stronglyAgree: 1
			}
		},
		{
			questionNumber: 13,
			questionText: 'Housing costs across Tulsa are too expensive.',
			votes: {
				stronglyDisagree: 0,
				disagree: 3,
				neutral: 9,
				agree: 7,
				stronglyAgree: 3
			}
		},
		{
			questionNumber: 14,
			questionText: 'My neighborhood has too many vacant homes.',
			votes: {
				stronglyDisagree: 2,
				disagree: 6,
				neutral: 4,
				agree: 8,
				stronglyAgree: 2
			}
		},
		{
			questionNumber: 15,
			questionText: 'The city cares about my neighborhood and its residents.',
			votes: {
				stronglyDisagree: 4,
				disagree: 8,
				neutral: 6,
				agree: 4,
				stronglyAgree: 0
			}
		},
		{
			questionNumber: 16,
			questionText: 'Tulsa needs more housing to succeed long-term.',
			votes: {
				stronglyDisagree: 1,
				disagree: 2,
				neutral: 7,
				agree: 5,
				stronglyAgree: 7
			}
		},
		{
			questionNumber: 17,
			questionText: 'I can receive adequate healthcare without leaving North Tulsa.',
			votes: {
				stronglyDisagree: 5,
				disagree: 10,
				neutral: 2,
				agree: 4,
				stronglyAgree: 1
			}
		},
		{
			questionNumber: 18,
			questionText: 'North Tulsa needs more food options for residents.',
			votes: {
				stronglyDisagree: 0,
				disagree: 1,
				neutral: 2,
				agree: 7,
				stronglyAgree: 12
			}
		}
	];
</script>

<div class="mx-auto prose max-w-3xl prose-h1:font-black prose-h2:text-3xl">
	<img src="moton ces collage.webp" alt="Collage of images from first engagement session" />
	<h1>Community Engagement Report</h1>
	<p class="italic">
		On March 6, 2026, the Terence Crutcher Foundation partnered with KB Advisory Group and
		PartnerTulsa to host the first community engagement session for the Moton Redevelopment Site. As
		community engagement work continues on this project, we will update this report to reflect as
		many community members' perspectives as possible.
	</p>
	<hr class="border-zinc-400" />
	<h2>Dreaming Exercise</h2>
	<p>
		Participants were asked to complete a <a
			href="/Dreaming Exercise.pdf"
			download="Dreaming Exercise.pdf">Dreaming Exercise</a
		> to reimagine what their neighborhood could look like and share any concerns they might have. Participants
		were asked five questions in total:
	</p>
	<ol>
		<li>What do you want this neighborhood to look like?</li>
		<li>What would success look like?</li>
		<li>What concerns do you have about redevelopment?</li>
		<li>What's missing from your neighborhood right now?</li>
		<li><em>Youth Only:</em> What would make you want to live here as an adult?</li>
	</ol>
	<h3>Community Priorities</h3>
	<p>
		Based on the feedback submitted in the Dreaming Exercise, the overarching goal for the community
		is to transform the Moton site into a self-sustaining, vibrant hub where residents can live,
		work, and thrive without needing to travel elsewhere for essential services. Success is defined
		by a sense of returning pride, safety, and economic mobility. Residents envision a neighborhood
		that feels like a destination in itself, characterized by well-maintained infrastructure, active
		community spaces, and an environment where families can raise children securely.
	</p>
	<strong>Local residents expressed four key priorities:</strong>
	<ul>
		<li>
			<strong>Essential Services & Retail:</strong> The most frequently cited gap is the lack of local
			grocery stores, healthy food options, full-service restaurants, and diverse retail shopping. Residents
			expressed a strong desire to avoid traveling outside of North Tulsa for these necessities.
		</li>

		<li>
			<strong>Infrastructure & Safety:</strong> There is a unanimous call for improved physical infrastructure,
			including better street lighting, paved sidewalks, parks, green spaces, and general beautification
			efforts.
		</li>

		<li>
			<strong>Economic Opportunity:</strong> The community emphasizes the need for local business growth,
			job opportunities, and educational resources that foster generational wealth. There is a specific
			desire for medical services and specialized businesses to be established locally.
		</li>

		<li>
			<strong>Community Spaces:</strong> Respondents want dedicated areas for social gathering, cultural
			events, classes, and youth activities.
		</li>
	</ul>
	<h3>Primary Concerns</h3>
	<p>
		While there is enthusiasm for redevelopment, significant anxiety surrounds the <em>process</em>
		and <em>impact</em> of changes:
	</p>

	<ul>
		<li>
			<strong>Gentrification & Displacement:</strong> A major point of contention is the fear that increased
			development and rising property values will price out long-time residents. Many respondents stressed
			that growth must be inclusive and that existing homeowners and renters should remain able to afford
			living in the neighborhood.
		</li>

		<li>
			<strong>Implementation & Trust:</strong> There is skepticism regarding whether new plans will actually
			be completed or delivered on schedule. Residents are concerned about the influence of outside developers
			versus local needs, requesting clear timelines and assurances that the vision aligns with community
			expectations.
		</li>

		<li>
			<strong>Balanced Development Types:</strong> There is a divergence in opinion regarding density.
			One segment of the community strongly advocates for mixed-use developments (combining housing, retail,
			and services) to create a lively center. Conversely, another group prefers maintaining a low-density,
			single-family residential character and opposes high-rise or heavy commercial construction in certain
			areas.
		</li>
	</ul>
	<h3>Youth Retention</h3>
	<p>
		To encourage young people to stay in the neighborhood as adults, safety for families, accessible
		entertainment, robust educational opportunities, and visible signs of community care and
		investment are critical factors.
	</p>
	<hr class="border-zinc-400" />
	<h2>Priority Ranking Exercise</h2>
	<p class="italic">
		Engagement session attendees were asked to mark their three top priorities for the Moton site
		after discussing with their peers.
	</p>
	<PrioritiesChart />
	<hr class="border-zinc-400" />
	<h2>Neighborhood Conditions Survey</h2>
	<p class="italic">
		These results are up to date as of March 22, 2026 and only include responses from those who live
		in the Moton area. Participants were asked to rate their agreement with each of the statements
		below. If you haven't taken the survey yet, do so <a href="/survey">here!</a>
	</p>
	<div id="legend" class="flex flex-wrap gap-x-4">
		{#each [['#d63434', 'Strongly Disagree'], ['oklch(80.8% 0.114 19.571)', 'Disagree'], ['oklch(85.2% 0.199 91.936)', 'Neutral'], ['oklch(69.6% 0.17 162.48)', 'Agree'], ['oklch(43.2% 0.095 166.913)', 'Strongly Agree']] as [color, label]}
			<div class="flex items-center gap-2">
				<div class="h-4 w-4 border border-zinc-400" style="background-color: {color}"></div>
				<p class="leading-0 font-bold text-black">{label}</p>
			</div>
		{/each}
	</div>
	{#each surveyResults as { questionNumber, questionText, votes }}
		<p class="font-bold text-black">{questionNumber}. {questionText}</p>
		<LikertChart classes="my-5 w-full" {votes} />
	{/each}
	<p></p>
</div>
