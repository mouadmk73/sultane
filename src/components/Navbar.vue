<template>
  <nav class="navbar">
    <div class="navbar-container">
      <router-link class="navbar-brand" to="/">My App</router-link>
      <button class="navbar-toggle" @click="toggleMenu">
        <span class="toggle-icon">☰</span>
      </button>
      <ul class="navbar-menu" :class="{ 'active': isMenuOpen }">
        <li class="navbar-item">
          <router-link class="navbar-link" to="/">Home</router-link>
        </li>
        <li class="navbar-item">
          <router-link class="navbar-link" to="/about">About</router-link>
        </li>
        <li class="navbar-item">
          <router-link class="navbar-link" to="/contact">Contact</router-link>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      isMenuOpen: false
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
    }
  }
}
</script>

<style scoped>
.navbar {
  background-color: #dc3545;
  padding: 1rem;
}

.navbar-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
}

.navbar-brand {
  color: white;
  font-size: 1.5rem;
  text-decoration: none;
}

.navbar-toggle {
  display: none;
  background: none;
  border: none;
  color: white;
  font-size: 1.5rem;
  cursor: pointer;
}

.navbar-menu {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
}

.navbar-item {
  margin-left: 1rem;
}

.navbar-link {
  color: white;
  text-decoration: none;
  padding: 0.5rem 1rem;
}

.navbar-link:hover {
  background-color: rgba(255, 255, 255, 0.1);
  border-radius: 4px;
}

@media (max-width: 768px) {
  .navbar-toggle {
    display: block;
  }

  .navbar-menu {
    display: none;
    flex-direction: column;
    width: 100%;
    text-align: center;
  }

  .navbar-menu.active {
    display: flex;
  }

  .navbar-item {
    margin: 0.5rem 0;
  }
}
</style>