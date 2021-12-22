<script lang='ts'>
	import MaterialButton from './components/MaterialButton.svelte';
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

<style global lang='scss'>
	@use '@material/button/styles';
</style>
