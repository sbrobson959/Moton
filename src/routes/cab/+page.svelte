<script>
	const MEMBERS = [
		{
			name: 'Bridget Jones',
			image: '/headshots/Bridget Jones.jpg',
			bio: "Bridget Jones is a lifelong resident of North Tulsa who is deeply rooted in her community.\n\nA proud graduate of The Booker T. Washington High School, she gives back by serving on the school's Distinguished Hall of Fame Committee, honoring the legacy and achievements of fellow graduates.\n\nBridget is an active member of Morning Star Baptist Church and proud resident of Dunbar Neighborhood, where she is committed to uplifting her neighbors and strengthening the community she calls home."
		},
		{
			name: 'DJ Mercer',
			image: '/headshots/DJ Mercer.jpg',
			bio: "DJ Mercer is a community advocate and proud North Tulsa homeowner who has dedicated more than a decade to serving the community he calls home. Since arriving to Tulsa in 2013, he has worked closely with families, students, and local leaders to help strengthen opportunities in North Tulsa. He spent seven years at Hawthorne Elementary, where he supported students and built lasting relationships within the community. As a father to a young son, this work is deeply personal. He is committed to building a North Tulsa where future generations have access to the resources, opportunities, and support they need to thrive right where they are. He believes no child should feel like they have to leave their community to succeed, and he works every day to help make that vision a reality."
		},
		{
			name: 'Joy Parnosky',
			image: '/headshots/Joy Parnosky.png',
			bio: "Joy has been a team member of Tulsa Public Schools for 17 years and originally began her career as a teacher. Joy is now Principal at Carver Middle School. In her current role, she works alongside school leaders and teachers to develop supports that help address the individual needs of students. She says that the best part of her job is that it allows her to serve others. She enjoys being able to \"help staff members strategize and create environments that cultivate compassion and connections within their school community.\""
		},
		{
			name: 'Tiffani Shaw',
			image: '/headshots/Tiffani Shaw.jpg',
			bio: "Tiffani Shaw is a criminal justice advocate and Employment Navigator at JusticeLink. A proud North Tulsa native, she graduated from Tulsa Central High School and is an active member of North Peoria Church of Christ. Having lived in North Tulsa her entire life, Tiffani has witnessed both the challenges and the resilience that shape her community. Her lived experiences have given her a deep understanding of diverse perspectives and life circumstances. Having overcome substance use, mental health struggles, and involvement in the criminal justice system, Tiffani now uses her story as a source of strength and purpose. Today, she is dedicated to restoring her community in the same way she was restored, through advocacy, support, and empowerment, and working to create opportunities and hope for those impacted by the justice system."
		},
		{
			name: 'Pastor Jean M. Neal',
			image: '/headshots/Jean Neal.jpeg',
			bio: "Pastor Jean M. Neal is a respected faith leader, community advocate, and visionary with more than 35 years of ministry and outreach experience. She served as Pastor of New Faith Baptist Church for 11 years and is the Founder and CEO of In His Image Discipleship Training Center, where she equips individuals for spiritual growth and leadership in alignment with Matthew 28:19–20.\n\nShe served for 12 years as Administrator and Program and Development Manager for the John Hope Franklin Center for Reconciliation, where she became a leading voice in education surrounding the 1921 Tulsa Race Massacre. Her work advanced public awareness and meaningful dialogue on both local and national levels. In recognition of her impact, she received a Pinnacle Award from the City of Tulsa. She also served as Board Vice President of Tulsa Metropolitan Ministry, addressing critical issues of diversity, inclusion, and unjust laws affecting the community, and contributed to the 1921 Race Massacre Commission, supporting planning efforts for the historic centennial commemoration.\n\nPastor Neal currently serves as Program Manager for Alzheimer's Diversity Outreach Services, Inc., leading initiatives that advance education, caregiver support, and health equity in underserved communities. In 2026, she expanded her leadership role as Advancement and Procurement Manager for The Tomorrow Foundation, overseeing grant development and sustainability efforts.\n\nA gifted speaker, mentor, and servant-leader, Pastor Neal is deeply committed to bridging faith and community impact. Above all, she is a devoted mother, grandmother, and great-grandmother whose life reflects resilience, compassion, and purpose."
		}
	];
</script>

<div class="mx-auto max-w-3xl">
	<h2 class="font-graebenbach my-5 text-4xl font-bold">Community Advisory Board</h2>

	<p class="mb-8 text-lg text-tcf-medium-gray">
		Meet the community members guiding the future of the Moton Site.
	</p>

	<div class="flex flex-col gap-10">
		{#each MEMBERS as { name, image, bio }}
			<div class="rounded-lg border border-gray-200 bg-white p-5 shadow-sm">
				<div class="flex flex-col sm:flex-row sm:items-start">
					<div class="shrink-0 sm:w-56">
						<img
							src={image}
							alt="{name} headshot"
							class="h-72 w-full rounded-lg object-cover"
						/>
					</div>
					<div class="flex flex-col pl-4">
						<h3 class="font-graebenbach-bold mb-3 text-2xl text-tcf-bg-gray">{name}</h3>
						<div class="prose max-w-none text-tcf-medium-gray">
							{#each bio.split('\n\n') as paragraph}
								<p class="mb-2">{paragraph}</p>
							{/each}
						</div>
					</div>
				</div>
			</div>
		{/each}
	</div>
</div>
