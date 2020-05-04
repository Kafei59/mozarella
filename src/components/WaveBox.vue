<template>
  <div class="box">
    <div class="box-title">
      <h1>Pierrick Gicquelais</h1>
      <h4>
        Software Engineer<br>
        Cloud Native
      </h4>
    </div>

    <div class="wave wave-one"></div>
    <div class="wave wave-two"></div>
    <div class="wave wave-three"></div>
  </div>
</template>

<script>
export default {
  name: 'WaveBox',
};
</script>

<style lang="scss" scoped>
.box {
  position: relative;
  overflow: hidden;
  width: 100%;
  min-height: 250px;
}

.wave {
  position: absolute;
  top: 3%;
  left: 50%;
  width: 2000px;
  height: 1900px;
  margin-left: -980px;
  margin-top: -1750px;
  opacity: 0.4;
  background: #0af;
  border-radius: 46%;
  animation: drift 5000ms infinite linear;
  z-index: 0;
}

.wave.wave-two {
  animation: drift 7000ms infinite linear;
  opacity: 0.1;
  background: #83ffee;
}

.wave.wave-three {
  animation: drift 5400ms infinite linear;
}

.box:after {
  content: '';
  display: block;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  z-index: 11;
}

@keyframes drift {
  from { transform: rotate(0deg); }
  from { transform: rotate(360deg); }
}

.box-title {
  position: absolute;
  z-index: 1;
  left: 40%;

  font-size: 1.5em;
  font-weight: bold;
  color: white;
}
</style>
