<template>
	<div class="search">
		<input class="input search__input" 
			type="text" 
			:value="modelValue"
			@input="updateInput">
	</div>
</template>

<script>
export default {
	props: {
		modelValue: [String]
	},
	methods: {
		updateInput(event) {
			this.$emit('update:modelValue', event.target.value);
		}
	}
}
</script>

<style lang="scss">
.input {
			width: 100%;
			padding: 15px 50px 15px 15px;
			border-radius: 25px;
			border: 2px solid #e3eef0;
			outline: none;
			position: relative;
		}
	.search__input{
		position: relative;
	}

	.search{
		position: relative;
		&::after {
				content: '';
				background: url(../../assets/search.png) no-repeat;
				width: 30px;
				height: 30px;
				position: absolute;
				top: 12px;
				right: 20px;
			}
	}
</style>