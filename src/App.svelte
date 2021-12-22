<script lang='ts'>
	import FeedbackList from './components/FeedbackList.svelte'
	import FeedbackStats from './components/FeedbackStats.svelte'

	let feedback = [
		{ id: 1, rating: 10,text: 'Enim eu turpis egestas pretium. Amet consectetur adipiscing elit ut aliquam purus sit amet. Leo vel fringilla est ullamcorper eget nulla facilisi etiam.'},
		{ id: 2, rating: 8,text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Et tortor at risus viverra adipiscing. Feugiat nisl pretium fusce id velit ut tortor pretium. Sagittis aliquam malesuada bibendum arcu vitae elementum curabitur.'},
		{ id: 3, rating: 7,text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Id neque aliquam vestibulum morbi blandit cursus risus. Ut pharetra sit amet aliquam id diam maecenas ultricies.'},
	]

	$: count = feedback.length
	$: average = feedback.reduce((a, {rating}) => a + rating, 0) / feedback.length
	$: ave = average.toFixed(2)

	const deleteFeedback = (e) => {
		const itemId = e.detail
		feedback = feedback.filter((item) => item.id != itemId)
	}
</script>

<main class='container'>
	<FeedbackStats 
		{count} 
		{ave} 
	/>
  <FeedbackList 
	  feedback={feedback} 
		on:delete-feedback={deleteFeedback}
	/>
</main>
