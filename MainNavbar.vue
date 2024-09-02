<template>
  <div class="navbar">
    <div class="icon">
      <h2 class="logo">W.Tech.</h2>
    </div>
    <div class="menu">
      <ul>
        <li v-for="(item, index) in menuItems" :key="index">
          <router-link :to="item.link">{{ item.name }}</router-link>
        </li>
      </ul>
    </div>
    <div class="search">
      <input class="srch" type="search" v-model="searchQuery" placeholder="Type To Find" />
      <button class="btn" @click="search">Find</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MainNavbar',
  data() {
    return {
      searchQuery: '',
      menuItems: [
        { name: 'HOME', link: '/' },
        { name: 'ABOUT', link: '/about' },
        { name: 'PROFILE', link: '/profile' },
        { name: 'PHOTOS', link: '/photos' },
      ],
    };
  },
  methods: {
    search() {
      alert(`Searching for: ${this.searchQuery}`);
    },
  },
};
</script>

<style scoped>
.navbar {
  width: 100%;
  height: 75px;
  margin: auto;
}

.icon {
  width: 200px;
  float: left;
  height: 70px;
}

.logo {
  color: #ff69b4;
  font-size: 20px;
  font-family: Cambria;
  padding-left: 50px;
  float: left;
  padding-top: 10px;
  margin-top: 5px;
}

.menu {
  width: 600px;
  float: left;
  height: 70px;
}

ul {
  float: left;
  display: flex;
  justify-content: center;
  align-items: center;
}

ul li {
  list-style: none;
  margin-left: 30px;
  margin-top: 27px;
  font-size: 14px;
}

ul li a {
  text-decoration: none;
  color: #ffc0cb;
  font-family: Arial;
  font-weight: bold;
  transition: 0.4s ease-in-out;
}

ul li a:hover {
  color: #ff1493;
}

.search {
  width: 330px;
  float: left;
  margin-left: 20px;
}

.srch {
  font-family: 'Times New Roman';
  width: 150px;
  height: 30px;
  background: transparent;
  border: 1px solid #ff1493;
  margin-top: 20px;
  color: #ffc0cb;
  border-right: none;
  font-size: 16px;
  float: left;
  padding: 10px;
  border-bottom-left-radius: 5px;
  border-top-left-radius: 5px;
}

.btn {
  width: 80px;
  height: 30px;
  background: #ff1493;
  border: 2px solid #ff1493;
  margin-top: 20px;
  color: #ffc0cb;
  font-size: 15px;
  border-bottom-right-radius: 5px;
  border-top-right-radius: 5px;
  transition: 0.2s ease;
  cursor: pointer;
}

.btn:hover {
  color: #000;
}

.btn:focus {
  outline: none;
}

.srch:focus {
  outline: none;
}
</style>
