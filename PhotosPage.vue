<template>
  <div class="photos">
    <div v-for="photo in filteredPhotos" :key="photo.id" class="photo">
      <img :src="photo.thumbnailUrl" :alt="photo.title" />
      <p>{{ photo.title }}</p>
    </div>
  </div>
</template>

<script>
import axiosInstance from '@/axious'; // Import the axios instance

export default {
  name: 'PhotosPage',
  data() {
    return {
      photos: [],
      searchQuery: ''
    }
  },
  computed: {
    filteredPhotos() {
      return this.photos.filter(photo => photo.title.includes(this.searchQuery)).slice(0, 10)
    }
  },
  methods: {
    fetchPhotos() {
      axiosInstance.get('/photos') // Use the axios instance here
        .then(response => {
          this.photos = response.data
        })
        .catch(error => {
          console.error('Error fetching photos:', error)
        })
    }
  },
  created() {
    this.fetchPhotos()
  }
}
</script>

<style scoped>
.photos {
  display: flex;
  flex-wrap: wrap;
  justify-content: center; /* Align photos horizontally */
}

.photo {
  margin: 10px;
  text-align: center;
  width: calc(20% - 20px); /* Adjust width to accommodate 5 photos per row */
}

img {
  width: 75%; /* Make images fill their container */
  height: auto; /* Maintain aspect ratio */
  border-radius: 5px; /* Add border-radius for a more aesthetic look */
}

p {
  color: #fff; /* Set title color to white */
  margin-top: 5px; /* Add some space between image and title */
  font-size: 14px; /* Adjust font size */
}
</style>

