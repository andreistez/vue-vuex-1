<template>
	<v-col cols="4">
		<v-card @click="openPhoto">
			<v-card-title>{{ photo.title }}</v-card-title>
			<v-card-text>
				<v-img
					:src="photo.url"
					width="200"
					height="200"
				/>
			</v-card-text>
		</v-card>
	</v-col>
</template>

<script>
import { mapMutations } from 'vuex'

export default {
	name: 'PhotoItem',
	props: {
		photo: {
			type: Object,
			required: true
		}
	},
	methods: {
		...mapMutations( ['setCurrentPhoto', 'showDialog'] ),
		openPhoto(){
			this.setCurrentPhoto( this.photo )
			this.showDialog()
		}
	}
}
</script>
