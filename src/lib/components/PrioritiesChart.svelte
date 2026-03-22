<script>
	import { Bar } from 'svelte-chartjs';
	import 'chart.js/auto';

	const labels = [
		'Restaurants',
		'Home Ownership',
		'Retail Shops',
		'Affordable Housing',
		'Youth Activities',
		'Cultural Features',
		'Small Business Space',
		'Community Space',
		'Other'
	];

	const voteData = [22, 21, 21, 17, 15, 15, 11, 8, 3];

	const data = {
		labels: labels,
		datasets: [
			{
				label: 'Votes',
				data: voteData,
				backgroundColor: '#d63434',
				borderColor: '#d63434',
				borderWidth: 1,
				borderRadius: 4
			}
		]
	};

	const options = {
		indexAxis: 'y',
		responsive: true,
		plugins: {
			title: {
				display: true,
				text: 'Priority Ranking Votes'
			},
			legend: {
				display: false
			},
			tooltip: {
				callbacks: {
					label: function (context) {
						const percent = (context.raw / 133) * 100;
						return `Votes: ${context.raw} (${percent.toFixed(2)}%)`;
					}
				}
			}
		},
		scales: {
			x: {
				beginAtZero: true
			}
		}
	};
</script>

<Bar {data} {options} />
