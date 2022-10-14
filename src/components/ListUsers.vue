<template>
  <div class="list">
			<User 
				v-for="user in users" :key="user.adress"
				:user="user"
			>
			</User>
			
	</div>
</template>

<script>
import User from './User.vue';

export default {
	components: { User },

	props: {
		users: {
			type: Array,
		}
	},

	data(){
		return {

		}
	},
	methods: {
		
	}
}
</script>

<style lang="scss">
.list{
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 20px;
	}
	
	@media (max-width: 980px) {
		.list{
			grid-template-columns: repeat(2, 1fr);
		}
	}

		@media (max-width: 685px) {
			.list {
				grid-template-columns: repeat(1, 1fr);
			}
		}
</style>