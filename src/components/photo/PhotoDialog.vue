<template>
	<v-dialog
		v-model="$store.getters.getDialogVisible"
		max-width="600"
		@click:outside="$store.commit( 'hideDialog' )"
	>
		<v-card>
			<v-card-title>{{ fullTitle }}</v-card-title>
			<v-card-text>
				<v-img :src="$store.getters.getCurrentPhoto.url" />
			</v-card-text>
		</v-card>
	</v-dialog>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
	name: 'PhotoDialog',
	computed: {
		fullTitle(){
			return `Photo's name - ${ this.getCurrentPhoto().title }`
		}
	},
	methods: {
		...mapGetters( ['getCurrentPhoto'] )
	}
}
</script>

<style scoped>

</style>