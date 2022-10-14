<template>
	<div class="popup" v-if="showed" @click="closeModal">
		<div class="popup-content">
			
			<div class="exit" @click="closeModal">✕</div>
			<div class="popup-inner" @click.stop>
				<div class="fio popup__fio">
					<span class="popup-fio">{{user.name}}</span>
				</div>
				<div class="popup-row">
					<span class="popup__leftside">Телефон:</span>
					<span class="popup__rightside telephone popup__rightside-telephone">{{ user.phone }}</span>
				</div>
				<div class="popup-row">
					<span class="popup__leftside ">Почта:</span>
					<span class="popup__rightside mail ">{{ user.email }}</span>
				</div>
				<div class="popup-row">
					<span class="popup__leftside">Дата приема:</span>
					<span class="popup__rightside text">{{ user.hire_date }}</span>
				</div>
				<div class="popup-row">
					<span class="popup__leftside">Должность:</span>
					<span class="popup__rightside text">{{ user.position_name }}</span>
				</div>
				<div class="popup-row">
					<span class="popup__leftside">Подразделение:</span>
					<span class="popup__rightside text">{{ user.department }}</span>
				</div>
				<div class="popup__leftside popup__info">
					Дополнительная информация:
					<div class="text popup__additionally">
						Lorem ipsum dolor sit amet consectetur, adipisicing elit. Eum quam autem dignissimos perspiciatis molestiae ratione commodi vero cumque facere blanditiis perferendis doloribus sunt, a obcaecati. 
						{{ user.address }}
					</div>
				</div>
			</div>

		</div>
	</div>
</template>

<script>
export default {
	props: {
		user: {
			type: Object,
		},	
		showed: {
			type: Boolean,
			default: false,
		}
	},
	data(){
		return{
			
		}
	},

	methods: {
		closeModal(){
			this.$emit('close')
		}
	}
}
</script>

<style lang="scss">
.popup{
	position: fixed;
	top: 0;
	left: 0;
	right: 0;
	bottom: 0;
	background: rgba(0, 0, 0, 0.3);
	display: flex;
	
		&-content{
			position: relative;
			margin: auto;
			width: 578px;
			padding: 50px 31px 40px 27px;
			background: #fff;
			border-radius: 20px;
		}
		
		&-row{
			display: grid;
			grid-template-columns: 3fr 4fr;
			margin-bottom: 20px;
		}

		&__rightside{
			color: #848484;
			text-align: left;
			text-overflow: ellipsis;
			overflow: hidden;
			white-space: nowrap;

			&-telephone{
				text-decoration: underline;
			}
		}

		&__leftside{
			font-size: 16px;
		}

		&-fio{
			font-size: 30px;
			
		}

		&__fio{
			margin-bottom: 58px;
		}

		&__additionally{
			text-align: justify;
			padding-top: 10px;
			font-size: 18px;
			color: #848484;
		}

		&__info{
			margin-top: 50px;
		}
	}

	.exit{
		font-weight: 100;
		position: absolute;
		top: -25px;
		left: 50%;
		transform: translateX(-50%);
		width: 50px;
		height: 50px;
		background: #b44ccf;
		border-radius: 50%;
		text-align: center;
		display: flex;
		justify-content: center;
		align-items: center;
		color: #fff;
		cursor: pointer;

		&:hover{
			opacity: 0.9;
			transition: 0.5s;
		}
	}

	.text{
		font-size: 14px;
	}
</style>