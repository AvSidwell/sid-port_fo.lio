<template>
  <div id="sidebar">
    <div class="sidebar-content">
      <div class="sidebar-header">
        <!-- Your Logo or Branding Here -->
        <img src="/path-to-your-logo.png" alt="Logo" />
      </div>
      <div class="sidebar-menu">
        <ul>
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/about">About</router-link></li>
          <li><router-link to="/services">Services</router-link></li>
          <li><router-link to="/portfolio">Portfolio</router-link></li>
          <li><router-link to="/contact">Contact</router-link></li>
        </ul>
      </div>
      <div class="sidebar-button">
        <button>Contact Us</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      view: {
        topOfPage: true,
      },
      activeLink: null,
    };
  },
  beforeMount() {
  window.addEventListener("scroll", this.handleScroll);
  this.handleScroll(); // Corrected this line
},

  beforeDestroy() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      if (window.pageYOffset > 0) {
        if (this.view.topOfPage) {
          this.view.topOfPage = false;
        }
      } else {
        if (!this.view.topOfPage) {
          this.view.topOfPage = true;
        }
      }
    },
  },
};
</script>

<style scoped>
* {
  color: #bfc0c6;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

#navbar {
  position: fixed;
  width: 100%;
  background-image: linear-gradient(rgba(0, 0, 0, 0.65), rgba(0, 0, 0, 0.65)),
    url(https://i.postimg.cc/T122XG3f/w123.jpg);
  background-size: cover; /* Ensure the background image covers the entire element */
  background-repeat: no-repeat;
  background-position: center;
  transition: all 0.2s ease-in-out;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  z-index: 2;
}

#sidebar {
  width: 250px;
  height: 100%;
  position: fixed;
  top: 0;
  left: 0;
  background: black;
  opacity: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.sidebar-content {
  padding: 20px;
  color: #fff;
}

.sidebar-header img {
  max-width: 100%;
}

.sidebar-menu ul {
  list-style-type: none;
  padding: 0;
}

.sidebar-menu ul li {
  margin: 10px 0;
}

.sidebar-menu ul li a {
  text-decoration: none;
  color: #fff;
  font-weight: 500;
  font-size: 16px;
  transition: color 0.3s;
}

.sidebar-menu ul li a:hover {
  color: #5bded6;
}

.sidebar-button button {
  background: #5bded6;
  color: #fff;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  font-weight: 500;
  cursor: pointer;
  transition: background 0.3s;
}

.sidebar-button button:hover {
  background: #fff;
  color: #5bded6;
}
</style>
