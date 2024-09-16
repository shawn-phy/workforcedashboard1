<template>
  <div id="app">
    <!-- Navbar or Global Header if needed -->
    <nav class="navbar">
      <i class="menu-icon"></i>
    </nav>
    
    <!-- Main Content Area -->
    <main>
      <Dashboard />
    </main>
  </div>
</template>

<script>
import { ref } from 'vue';
import Dashboard from './components/Dashboard.vue';

export default {
  name: 'App',
  components: {
    Dashboard,
  },
  setup() {
    const showMenu = ref(false);

    const toggleMenu = () => {
      showMenu.value = !showMenu.value;
    };

    return {
      showMenu,
      toggleMenu,
    };
  },
};
</script>

<style scoped>
#app {
  font-family: 'Arial', sans-serif;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.navbar {
  background-color: #333;
  color: white;
  padding: 10px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
}

.menu-icon {
  font-size: 24px;
  cursor: pointer;
}

main {
  flex: 1;
  padding: 20px;
}
</style>
