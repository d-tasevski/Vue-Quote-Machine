<template>
	<div class="container">
		<Header :quote-count="quotes.length" :max-quotes="maxQuotes"> </Header>
		<NewQuote @quoteAdd="newQuoteAdd"></NewQuote>
		<QuoteGrid :quotes="quotes" @quoteDeleted="deleteQuote"></QuoteGrid>
		<div class="row">
			<div class="col-sm-12 text-center">
				<div class="alert alert-info">
					Info: Click on a quote to delete it.
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue'
import NewQuote from './components/NewQuote.vue'
import Header from './components/Header.vue'

export default {
	data(){
		return {
			maxQuotes: 10,
			quotes: [
				'Love For All, Hatred For None. – Khalifatul Masih III',
				'Change the world by being yourself. – Amy Poehler',
				'Every moment is a fresh beginning. – T.S Eliot',
				'Never regret anything that made you smile. – Mark Twain',
				'Die with memories, not dreams. – Unknown',
				'Aspire to inspire before we expire. – Unknown',
				'Everything you can imagine is real. – Pablo Picasso',
				'Simplicity is the ultimate sophistication. – Leonardo da Vinci',
				'Whatever you do, do it well. – Walt Disney'
			]
		}
	},
	components: {
		QuoteGrid: QuoteGrid,
		NewQuote: NewQuote,
		Header: Header
	},
	methods: {
		newQuoteAdd(quote){
			if (this.quotes.length >= this.maxQuotes) {
				 alert('Please remove some quotes')
			}else {
				this.quotes.unshift(quote);
			}
		},
		deleteQuote(index){
			this.quotes.splice(index, 1);
		}
	}
}
</script>

<style>
</style>
