<script lang='ts'>
	import MaterialButton from './components/MaterialButton.svelte';

	const formValues = {
		name: '',
		profileSummary: '',
		country: '',
		jobLocation: [],
		remoteWork: false,
		skillSet: [],
	}
</script>

<MaterialButton 
  id='one' 
  text='Button no 1'
	onClickFunction={() => {
		console.log('You just clicked button no 1')
	}}
/>
<MaterialButton 
  id='two' 
  text='Button no 2'
	onClickFunction={() => {
		console.log('You just clicked button no 2')
	}}
/>

<main>
	<form>
		<div class='code'>
			<pre>{JSON.stringify(formValues, null, 2)}</pre>
		</div>

		<div>
			<label for='name'>Name</label>
			<input type='text' id='name' bind:value={formValues.name} />
		</div>

		<div>
			<label for='profile'>Profile Summary</label>
			<textarea id='profile' bind:value={formValues.profileSummary} />
		</div>

		<div>
			<label for='country'>Country</label>
			<select id='country' bind:value={formValues.country}>
				<option value=''>Select a country</option>
				<option value='india'>India</option>
				<option value='vietnam'>Vietnam</option>
				<option value='japan'>Japan</option>
				<option value='united-states'>United States</option>
			</select>
		</div>

		<div>
			<label for='job-location'>Job Location</label>
			<select id='country' bind:value={formValues.jobLocation} multiple>
				<option value=''>Select a country</option>
				<option value='india'>India</option>
				<option value='vietnam'>Vietnam</option>
				<option value='japan'>Japan</option>
				<option value='united-states'>United States</option>
			</select>
		</div>

		<div class='oneline'>
			<label for='remoteWork'>Are you willing to work remotely?</label>
			<input type='checkbox' id='remoteWork' bind:checked={formValues.remoteWork} />
		</div>

		<div class='oneline'>
			<label for='skillSet'>Skill set</label>
			<div class='selection'>
				<input type='checkbox' id='html' value='html' bind:group={formValues.skillSet} />
				<label for='html'>Html</label>
			</div>
			<div class='selection'>
				<input type='checkbox' id='css' value='css' bind:group={formValues.skillSet} />
				<label for='css'>CSS</label>
			</div>
			<div class='selection'>
				<input type='checkbox' id='javascript' value='javascript' bind:group={formValues.skillSet} />
				<label for='javascript'>Javascript</label>
			</div>
		</div>
	</form>
</main>

<style global lang='scss'>
	@use '@material/button/styles';

	main {
		margin: 0.7rem;
		padding: 0.7rem;
	}

	.code {
		display: flex;
		flex-direction: row;
		height: 200px;
	}

	div {
		margin: 0.7rem 0;
		padding: 0.4rem 0;
		display: flex;
		flex-direction: column;
		width: 33%;
	}

  .oneline {
		width: 33%;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
	}

	.selection {
		display: inline;
	}
</style>
