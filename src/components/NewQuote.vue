<template>
	<form class="row">
		<div class="form-group col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
			<label for="quote">Quote</label>
			<textarea class="form-control" v-model="quote" name="quote" id="quote" cols="30" rows="5"></textarea>
		</div>
		<div class="form-group col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
			<button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
		</div>
	</form>
</template>

<script>
export default {
	data(){
		return {
			quote: ''
		}
	},
	methods: {
		createNew(){
			this.$emit('quoteAdd', this.quote); 
			this.quote = '';
		}
	}
}
</script>

<style>
</style>
