<template>
  <div id="app">
    <transition name="fade">
      <loader v-if="loading"></loader>
      <el-container v-else>
        <el-container>
          <el-main id="main">
            <wave-box/>

            <transition name="fade" mode="out-in">
              <router-view></router-view>
            </transition>

            <el-backtop target="#main"></el-backtop>
          </el-main>

          <el-footer height="10px" class="white">
            <p>
              <span class="float-left">Developped with Vue | Enhanced with Element UI</span>
              <span class="float-right">Updated in May, 2020.</span>
            </p>
          </el-footer>
        </el-container>
      </el-container>
    </transition>
  </div>
</template>

<script>
import Loader from './components/Loader.vue';
import WaveBox from './components/WaveBox.vue';

export default {
  name: 'app',
  components: { Loader, WaveBox },

  data() {
    return {
      loading: true,
    };
  },

  mounted() {
    setTimeout(() => {
      this.loading = false;
    }, 1500);
  },
};
</script>

<style lang="scss">
body {
  background-color: #465365;
  color: white;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#main {
  height: 92vh;
  overflow-y: scroll;
  background-color: #f7f7f7;
  padding: 0;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s
}

.fade-enter, .fade-leave-to {
  opacity: 0
}

.main-text {
  font-size: 1.1em;
}

.card {
  box-shadow: 0 30px 60px 0 rgba(90, 116, 148, 0.4);
  border-radius: 10px;
  padding: 15px;
  margin: 20px;

  .el-card__body {
    padding: 0;
  }

  .card-title {
    font-size: 1.5em;
    padding-left: 15px;
    font-weight: lighter;
  }

  .card-body {
    font-size: 1.1em;
    padding-top: 20px
  }

  .card-footer {
    padding: 18px 20px;
  }
}

.text-left {
  text-align: left;
}

.text-center {
  text-align: center;
}

.text-justify {
  text-align: justify;
}

.text-right {
  text-align: right;
}

.float-left {
  float: left;
}

.float-right {
  float: right;
}

.white {
  color: white;
}
</style>
