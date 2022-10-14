<template>
	<form 
			class="form"
			@submit.prevent
		>
		<Search 
			v-model="query"
			@input="$emit('search', query)"
		/>
	</form>
</template>

<script>
import Search from "./UI/Search.vue";

export default {
  components: { Search },
	data() {
		return {
			query: "",
		}
	},
}
</script>

<style lang="scss">



</style>