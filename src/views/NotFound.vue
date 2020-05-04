<template>
  <div>
    <p class="main-text">
      Oh 😰, you entered a non-safe zone also called <strong>404 NOT FOUND</strong> ⛔️ space.<br/>
      You try to enter something silly in the address bar, don't you ? 😈<br/>
      Anyway, I will lead you to the nearest safe road.<br/><br/>

      <router-link to="/">
        <el-button type="primary">Get me back to the main page ! 👋</el-button>
      </router-link>&nbsp;&nbsp;
    </p>

    <div>
      <img src="../assets/bongo-cat.gif" width="256" style="opacity: 0.3"/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NotFound',
};
</script>
