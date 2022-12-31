<template>
	<v-container>
		<PhotoForm v-if="$store.getters.getPhotos.length < 11" @addPhoto="addPhoto" />
		<div v-else>Can't add more photos.</div>
		<v-row>
			<PhotoItem
				v-for="photo in $store.getters.getPhotos"
				:key="photo.id"
				:photo="photo"
			/>
		</v-row>
		<PhotoDialog />
	</v-container>
</template>

<script>
import PhotoItem from '@/components/photo/PhotoItem'
import PhotoForm from '@/components/photo/PhotoForm'
import PhotoDialog from '@/components/photo/PhotoDialog'
import { mapActions } from 'vuex'

export default {
	name: 'PhotosPage',
	components: {
		PhotoItem,
		PhotoForm,
		PhotoDialog
	},
	data: () => ( {
		photos: [],
		currentPhoto: {},
		dialogVisible: false
	} ),
	mounted(){
		this.fetchPhotos()
	},
	methods: {
		...mapActions( ['fetchPhotos'] ),
		addPhoto( photo ){
			this.photos.push( photo )
		},
		openPhoto( photo ){
			this.currentPhoto = photo
			this.dialogVisible = true
		}
	}
}
</script>
