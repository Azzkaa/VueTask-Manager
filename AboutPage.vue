<template>
  <div class="background">
    <div class="content">
      <h1>About</h1>
      <table class="profile-table">
        <tr>
          <td>Name:</td>
          <td>{{ profile.name }}</td>
        </tr>
        <tr>
          <td>Course Year:</td>
          <td>{{ profile.courseYear }}</td>
        </tr>
        <tr>
          <td>Matrix No.:</td>
          <td>{{ profile.matrixNo }}</td>
        </tr>
        <tr>
          <td>Address:</td>
          <td>{{ profile.address }}</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex';

export default {
  name: 'AboutPage',
  computed: {
    ...mapGetters(['getProfile']),
    profile() {
      return this.getProfile;
    }
  }
}
</script>

<style scoped>
.background {
  background-image: url('https://images.pexels.com/photos/376533/pexels-photo-376533.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1');
  background-position: center;
  background-size: cover;
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.content {
  width: 400px;
  padding: 20px;
  background-color: rgba(51, 51, 51, 0.8); 
  border-radius: 10px;
  margin-top: -75px; /* Adjust the margin-top to move the content up */
}

.profile-table {
  margin-top: 20px;
  border-collapse: collapse;
  width: 300px;
}

.profile-table td {
  padding: 10px;
  border-bottom: 3px solid #ffc0cb;
  color: #ffc0cb; /* Set label text color to white */
}

.profile-table td:first-child {
  font-weight: bold;
}

.profile-table td:last-child {
  text-align: right;
}

.profile-table tr:last-child td {
  border-bottom: none;
}

/* Pink color for text fields' data */
.profile-table td:nth-child(2) {
  color: white;
}


/* Pink color for the "About" heading */
.content h1 {
  color: #ff1493;
}
</style>
