<template>
	<div class="user" @click="show">
		<div class="fio user__fio"> {{ user.name }} </div>
		<div class="info">
			<div class="tepelphone user__telephone"> 
				<img src="../assets/phone.png" class="info__img" alt=""> 
				{{ user.phone }} 
			</div>
			<div class="mail user__mail "> 
				<img src="../assets/mail.png" class="info__img" alt="mail" > 
				{{ user.email }} 
			</div>
		</div>
		<Popup 
			:user="user" 
			:showed="showed"
		/>
	</div>
	
</template>

<script>
import Popup from './UI/Popup.vue';

export default {
	components: { Popup },

    props: {
        user: {
            type: Object,
        }
    },
    data() {
        return {
            showed: false,
        };
    },
    methods: {
        show() {
            this.showed = !this.showed;
            console.log(this.showed);
        },

			toogleModal() {
				this.isShowModal = !this.isShowModal;
			}
    },
    
}
</script>

<style lang="scss">
.user{
		padding: 39px 27px;
		background: #fff;
		border-radius: 20px;
		cursor: pointer;
		height: 315px;
		font-size: 20px;
		font-family: 'Arial';
		box-shadow: 6px 10px 8px 8px rgba(34, 60, 80, 0.06);
		&__fio{
			margin-bottom: 52px;
		}

		&__telephone{
			margin-bottom: 20px;	
		}
	}

	.info{
		&__img{
			vertical-align: top;
			margin-right: 15px;
		}
	}
	.fio{
		font-weight: 600;
			font-size: 22px;
	}
	
	.telephone{
		font-size: 18px;
	}

	.mail{
		font-size: 15px;
		text-decoration: underline;
	}

	.info{
		color: #848484;
	}
</style>