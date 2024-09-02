<template>
  <div class="background">
    <div class="content">
      <h1>Profile</h1>
      <form @submit.prevent="saveProfile" class="profile-form">
        <div class="form-row">
          <label for="name" class="label">Name:</label>
          <input type="text" v-model="profile.name" />
        </div>
        <div class="form-row">
          <label for="courseYear" class="label">Course Year:</label>
          <input type="text" v-model="profile.courseYear" />
        </div>
        <div class="form-row">
          <label for="matrixNo" class="label">Matrix No.:</label>
          <input type="text" v-model="profile.matrixNo" />
        </div>
        <div class="form-row">
          <label for="address" class="label">Address:</label>
          <input type="text" v-model="profile.address" />
        </div>
        <button type="submit">Save</button>
        <button type="button" @click="resetProfile">Reset</button>
      </form>
    </div>
  </div>
</template>

<script>
import { mapState, mapActions } from 'vuex';

export default {
  name: 'ProfilePage',
  computed: {
    ...mapState(['profile']),
  },
  methods: {
    ...mapActions(['resetProfileAction']),
    resetProfile() {
      // Dispatch action to reset the profile to its initial values
      this.resetProfileAction();
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
  padding: 30px;
  background-color: rgba(51, 51, 51, 0.8); /* Semi-transparent background to improve readability */
  border-radius: 10px;
  margin-top: -75px;
}

.form-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 15px;
}

.label {
  flex: 1;
  margin-right: 10px;
  color: #fff; /* Set label color to white */
}

input {
  flex: 2;
  padding: 8px;
  border-radius: 5px;
  border: 1px solid #ffc0cb;
  background-color: #1e1e1e;
  color: #ffc0cb;
}

button {
  padding: 8px 16px;
  border: none;
  border-radius: 5px;
  background-color: #ff1493;
  color: #fff;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #ff007f;
}

.content h1 {
  color: #ff1493;
}

</style>
