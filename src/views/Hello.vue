<template>
  <div>
    <p class="main-text">
      Hi 👋, my name is <strong>Pierrick Gicquelais</strong>,
      I am a <strong>Software Engineer</strong> from France 🇫🇷.<br/>
      I graduated from Epitech computer science school
      for a <strong>Bachelor's Degree</strong> 🏛 in 2017.<br/>
      Ever since, I always work for and with APIs, always trying new technologies.<br/>
      Here, you will be able to find the list of skills I try to develop and any
      way to contact me. <br/>
      You find the sources of this site
      <a href="https://github.com/Kafei59/mozarella" target="_blank">here</a> 👀.
    </p>

    <el-row>
      <el-col :md="8">
        <el-card class="card">
          <div slot="header" class="clearfix card-title">
            <img src="../assets/resume-128x128.png" width="32">
            Resume
          </div>

          <div class="card-body">
            <p>
              If you want to know where I mostly work in my life, go ahead.
            </p>
          </div>

          <div class="card-footer">
            <router-link to="/resume">
              <el-button type="primary">Let me see ! 👀</el-button>
            </router-link>
          </div>
        </el-card>
      </el-col>

      <el-col :md="8">
        <el-card class="card">
          <div slot="header" class="clearfix">
            <img src="../assets/magic-wand-128x128.png" width="32">
            <span class="card-title">Skills</span>
          </div>

          <div class="card-body">
            <p>
              If you want to see what I am capable of, you can check this out.
            </p>
          </div>

          <div class="card-footer">
            <router-link to="/skills">
              <el-button type="primary">I am interested ! 👍</el-button>
            </router-link>
          </div>
        </el-card>
      </el-col>

      <el-col :md="8">
        <el-card class="card">
          <div slot="header" class="clearfix">
            <img src="../assets/paper-plane-128x128.png" width="32">
            <span class="card-title">Contact</span>
          </div>

          <div class="card-body">
            <p>
              If you want to write me a pleasant letter, you know what to do.
            </p>
          </div>

          <div class="card-footer">
            <router-link to="/contact">
              <el-button type="primary">It will be a pleasure ! 🤝</el-button>
            </router-link>
          </div>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: 'Hello',
};
</script>

<style lang="scss" scoped>
</style>
