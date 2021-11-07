<template>
  <div>
    <el-row>
      <el-col :span="24"
        ><div class="grid-content bg-purple-dark">
          <div class="top-links container">
            <ul class="d-flex">
              <li>
                <nuxt-link to="/"
                  >kphp,Hyderabad. <span class="ml-3">|</span></nuxt-link
                >
              </li>
              <li>
                <nuxt-link to="/"
                  >hr@rdsinfotech.com <span class="ml-3">|</span></nuxt-link
                >
              </li>
              <li>
                <nuxt-link to="/">+91 40-29563887</nuxt-link>
              </li>
            </ul>
          </div>
        </div></el-col
      >
    </el-row>
    <header class="navbar" v-bind:class="{ scroll: scrollPosition > 200 }">
      <div class="navbar-navs">
        <nuxt-link to="/" class="logo">
          <img src="/favicon.png" alt="" />
        </nuxt-link>
        <div class="nav-items">
          <ul class="d-flex">
            <li>
              <nuxt-link to="/">
                <fa
                  :icon="['fa', 'home']"
                  style="font-size: 20px"
                  :style="{ color: '#444', background: '#fff' }"
                />
              </nuxt-link>
            </li>
            <li>
              <nuxt-link to="/about">ABOUT</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/whyrds">WHY RDS</nuxt-link>
            </li>

            <li>
              <nuxt-link to="/">SERVICES</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/">PROJECTS</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/">CAREERS</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/contact-us">CONTACT</nuxt-link>
            </li>
          </ul>
        </div>
        <!-- Mobile Header -->
        <div class="mobile-menu-container" :class="{ active: showMobileMenu }">
          <nav class="nav-items1">
            <ul>
              <li>
                <nuxt-link class="mobile-links" to="/">HOME</nuxt-link>
              </li>
              <li>
                <nuxt-link class="mobile-links" to="/about">ABOUT </nuxt-link>
              </li>
              <li>
                <nuxt-link class="mobile-links" to="/whyrds">Why RDS</nuxt-link>
              </li>
              <li>
                <nuxt-link class="mobile-links" to="/services">
                  SERVICES</nuxt-link
                >
              </li>
              <li>
                <nuxt-link class="mobile-links" to="/Projects"
                  >PROJECTS</nuxt-link
                >
              </li>
              <li>
                <nuxt-link class="mobile-links" to="/careers"
                  >CAREERS</nuxt-link
                >
              </li>
              <li>
                <nuxt-link class="mobile-links" to="/contact-us"
                  >CONTACT US</nuxt-link
                >
              </li>
            </ul>
          </nav>
        </div>
        <button
          class="toggle-btn"
          @click="showMobileMenu = !showMobileMenu"
          style="
            display: flex;
            align-items: center;
            justify-content: center;
            background: #fff;
            border: none;
            display: none;
          "
        >
          <span class="toggle-icon" v-if="!showMobileMenu">
            <fa
              :icon="['fa', 'bars']"
              style="font-size: 30px"
              :style="{ color: '#444', background: '#fff' }"
            />
          </span>
          <span class="close-icon" v-if="showMobileMenu">
            <fa
              :icon="['fa', 'window-close']"
              style="font-size: 30px"
              :style="{ color: '#444', background: '#fff' }"
            />
          </span>
        </button>
      </div>
    </header>

    <div>
      <Nuxt />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      scrollPosition: null,
      showMobileMenu: false,
    }
  },
  mounted() {
    window.addEventListener('scroll', this.updateScroll)
  },
  methods: {
    updateScroll() {
      this.scrollPosition = window.scrollY
    },
  },
}
</script>
<style>
.navbar {
  padding: 0 1em;
}
.navbar-navs {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
}
.navbar-brand {
  padding: 0;
}
.navbar-dark .navbar-text {
  color: #000000;
  font-weight: 600;
  font-size: 1em;
}
.grid-content {
  background: #000;
  min-height: 40px;
}
ul {
  margin-bottom: 0 !important;
  align-items: center;
}
ul li {
  margin-right: 1.7em;
}
li a {
  color: #000000;
  font-weight: 600;
}
a:hover {
  text-decoration: none;
}
.top-links {
  display: flex;
  align-items: center;
  min-height: 40px;
}
.top-links li a {
  color: #fff;
  font-weight: 400;
}

.scroll {
  position: fixed;
  width: 100%;
  top: 0;
  left: 0;
  background: #fff;
  box-shadow: 0 0 10px 3px rgba(34, 33, 33, 0.1);
  -webkit-transition: 0.5s ease-in-out;
  transition: 0.5s ease-in-out;
  animation: affix_animation 0.6s ease-in-out;
  -webkit-animation: affix_animation 0.6s ease-in-out;
  z-index: 99;
}
@-webkit-keyframes affix_animation {
  0% {
    margin-top: -7.5rem;
    opacity: 0;
  }
  50% {
    margin-top: -4rem;
    opacity: 0;
  }
  100% {
    margin-top: 0rem;
    opacity: 1;
  }
}
@keyframes affix_animation {
  0% {
    margin-top: -7.5rem;
    opacity: 0;
  }
  50% {
    margin-top: -4rem;
    opacity: 0;
  }
  100% {
    margin-top: 0rem;
    opacity: 1;
  }
}
/* .toggle-icon {
  display: none;
}
.close-icon {
  display: none;
} */
.mobile-menu-container {
  display: none;
}
@media (max-width: 992px) {
  .nav-items {
    display: none;
  }
  .toggle-icon {
    display: block;
  }
  .toggle-btn {
    display: block !important;
  }
  /* Mobile menu */
  .mobile-menu-container {
    position: absolute;
    display: block;
    width: 100%;
    z-index: 999;
    background: #fff;
    top: 102%;
    height: auto;
    left: 0;
    list-style: none;
    padding: 3em;
    display: flex;
    justify-content: center;
    align-items: center;
    visibility: hidden;
    margin-top: 50vh;
    transition: all 0.5s ease-in-out;
    border-top: 1px solid rgba(0, 0, 0, 0.05);
    border-bottom: 1px solid rgba(0, 0, 0, 0.1);
  }

  .nav-items1 {
    text-align: center;
  }
  .nav-items1 ul li {
    list-style: none;
    margin-bottom: 13px;
    position: relative;
  }
  .active {
    transform: translateX(0);
    visibility: visible;
    margin-top: 0;
  }
}
@media (max-width: 768px) {
  .top-links {
    max-width: 100%;
  }
}
@media (max-width: 576px) {
  .grid-content {
    display: none;
  }
}
</style>
