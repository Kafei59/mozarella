<template>
  <div>
    <p class="main-text">
      I will be pleased to discuss with you on any matters.<br/>
      You can reach me via e-mail through this
      <a href="mailto:pierrick.gicquelais@gmail.com">address</a> 📩<br/>
      Otherwise, you can directly send me a private message through Linkedin
      <a href="https://www.linkedin.com/in/pierrick-gicquelais/" target="_blank">here</a> 📝<br/>
      Or, if you want to see all my stuff and projects, you can check my Github page
      <a href="https://github.com/Kafei59" target="_blank">here</a> 🦊<br/><br/>

      <router-link to="/">
        <el-button type="primary">Get me back to the main page ! 👋</el-button>
      </router-link>&nbsp;&nbsp;

      <router-link to="/resume">
        <el-button type="primary">Oh no, I did not check your resume ! 📄️</el-button>
      </router-link>&nbsp;&nbsp;

      <router-link to="/skills">
        <el-button type="primary">Oops, no I want to check your skills ! ⚡️</el-button>
      </router-link>&nbsp;&nbsp;
    </p>

    <div>
      <p class="main-text">
        And if you want, we can also grab a <strong>beer</strong> 🍻
        or some <strong>cheese</strong> 🧀 with <strong>pizza</strong> 🍕 in Lille where I live<br/>
        (If you do not know where it is, here is an hint:)
      </p>
    </div>

    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d40492.601738702295!2d3.0121411145855417!3d50.63106225206021!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47c2d579b3256e11%3A0x40af13e81646360!2sLille!5e0!3m2!1sfr!2sfr!4v1588611974715!5m2!1sfr!2sfr"
            width="600" height="350" frameborder="0" style="border:0;"
            allowfullscreen="" aria-hidden="false" tabindex="0"/>
  </div>
</template>

<script>
export default {
  name: 'Contact',

  data() {
    return {
      center: {
        lat: 50.633333,
        lng: 3.066667,
      },
      zoom: 6,
      markers: [{
        position: {
          lat: 50.6381373,
          lng: 3.061137599999938,
        },
      }],
    };
  },
};
</script>
