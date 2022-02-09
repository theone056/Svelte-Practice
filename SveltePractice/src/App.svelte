<script>
	import FeedbackList from './components/FeedbackList.svelte';
	import FeedbackStats from './components/FeedbackStats.svelte';

	let feedback = [
		{
			id:1,
			rating:10,
			text: 'Incididunt labore officia duis consectetur duis qui consequat ullamco consequat sunt ad. Labore culpa tempor esse labore cupidatat. Nisi cupidatat aliquip reprehenderit ipsum eu aliqua eiusmod officia ipsum exercitation. Sunt adipisicing eiusmod in pariatur ipsum nisi ut dolore nulla. Irure eiusmod esse pariatur elit. Minim qui laborum in elit Lorem anim laboris ullamco ea dolor ut proident. Id laborum laborum dolor fugiat.'
		},
		{
			id:2,
			rating:9,
			text:'Voluptate sit laborum commodo cupidatat eu quis est. Reprehenderit aliqua tempor qui laborum labore culpa consequat id eiusmod esse sint irure magna qui. Veniam dolor ea consequat ex ullamco velit consequat adipisicing veniam non. Nisi cillum ea est sint laboris duis laborum pariatur voluptate id culpa. Non excepteur ex irure sit nulla id exercitation. Qui elit mollit incididunt exercitation velit cillum ipsum proident aute fugiat. Dolore do nisi reprehenderit labore dolor est proident est dolore nostrud adipisicing.'
		},
		{
			id:3,
			rating:8,
			text:'Pariatur Lorem cillum irure dolore deserunt ea. Nisi dolore exercitation adipisicing tempor cillum in. Qui id aliquip eiusmod deserunt do proident ad et excepteur aliqua occaecat adipisicing sit.'
		}
	]

	$: count = feedback.length;
	$: average = feedback.reduce((prev,{rating})=>prev + rating,0)/feedback.length;

	const deleteFeedback = (e) => {
		let itemId = e.detail;
		feedback = feedback.filter(item=> item.id != itemId);
	}
</script>

<main class="container">
	<FeedbackStats {count} {average}/>
	<FeedbackList {feedback} on:delete-feedback={deleteFeedback}/>
</main>

<style>
</style>