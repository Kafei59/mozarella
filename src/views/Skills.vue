<template>
  <div>
    <p class="main-text">
      Since it has been multiple years I worked in IT,
      I had the opportunity to test several technologies.<br/>
      Nowadays, I mainly focus myself on <strong>Cloud Native</strong> ☁️ softwares
      and <strong>Orchestration</strong> ⛴<br/>
      I also tend to be more confident in <strong>Golang</strong> 🦝 environment and
      <strong>HTTP/2 protocols (gRPC)</strong><br/><br/>

      <router-link to="/">
        <el-button type="primary">Get me back to the main page ! 👋</el-button>
      </router-link>&nbsp;&nbsp;

      <router-link to="/resume">
        <el-button type="primary">This is cool but let see your resume ! 📄️</el-button>
      </router-link>&nbsp;&nbsp;

      <router-link to="/contact">
        <el-button type="primary">Wow, where can we reach you ? 📩</el-button>
      </router-link>
    </p>

    <el-row :span="24">
      <el-col :lg="{span: 17, offset: 3}">
        <el-tabs v-model="tab" @tab-click="ChangeTab" class="skills">
          <el-tab-pane label="Software Engineering" name="software"/>
          <el-tab-pane label="DevOps" name="devops"/>
          <el-tab-pane label="Web Development" name="web"/>
          <el-tab-pane label="Others" name="other"/>
        </el-tabs>

        <el-row  :span="24">
          <el-col :lg="12" v-for="(skill, index) in skills[tab]" :key="index">
            <el-card class="card">
              <div slot="header" class="clearfix text-center card-title">
                <img :src="GetImage(skill.image)" width="32">
                {{ skill.name }}
              </div>

              <div class="card-body">
                <p>{{ skill.description }}</p>
              </div>

              <div class="card-footer">
                <el-progress :show-text="false" :stroke-width="18" :percentage="skill.percent"/>
              </div>
            </el-card>
          </el-col>
        </el-row>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: 'Skills',

  methods: {
    ChangeTab(tab) {
      this.tab = tab.name;
    },

    GetImage(img) {
      // eslint-disable-next-line global-require,import/no-dynamic-require
      return require(`../assets/tech/${img}`);
    },
  },

  data() {
    return {
      tab: 'software',
      skills: {
        software: [
          {
            name: 'Golang',
            percent: 90,
            image: 'golang-256x256.png',
            description: 'Currently working with this environment. Used for easy router and async tasking.',
          },
          {
            name: 'gRPC',
            percent: 70,
            image: 'grpc-256x256.png',
            description: 'Using Buffer Protocol for APIs efficiency using HTTP/2.',
          },
          {
            name: 'CI/CD',
            percent: 95,
            image: 'gitlab-256x256.png',
            description: 'Github jobs, Gitlab, Jenkins ... anyone you name it, I use it.',
          },
          {
            name: 'Python',
            percent: 80,
            image: 'python-256x256.png',
            description: 'Used as API framework through Flask and for easily scripting data.',
          },
          {
            name: 'postgreSQL',
            percent: 75,
            image: 'pg-256x256.png',
            description: 'I am mostly using relational schemas for databases but I already worked a lot with MongoDB as well.',
          },
          {
            name: 'C/C++',
            percent: 65,
            image: 'cpp-256x256.png',
            description: 'Learned from school, still have some projects using them.',
          },
        ],
        devops: [
          {
            name: 'Kubernetes',
            percent: 80,
            image: 'kubernetes-256x256.webp',
            description: 'Main orchestration framework I use on my platforms. I also develop operators for them.',
          },
          {
            name: 'Docker',
            percent: 80,
            image: 'docker-256x256.png',
            description: 'Nowadays, everything is made through containers, Docker is a must-have in our toolbox.',
          },
          {
            name: 'OpenStack',
            percent: 70,
            image: 'openstack-256x256.png',
            description: 'I tend to use all the tools offered by OpenStack in my cloud driven perspective.',
          },
          {
            name: 'Cadence',
            percent: 50,
            image: 'uber-256x256.webp',
            description: 'Uber framework to orchestrate a lot of workflows processing, great tool.',
          },
          {
            name: 'Kafka',
            percent: 80,
            image: 'kafka-256x256.png',
            description: 'All my streaming processes are mainly filtered by Kafka.',
          },
          {
            name: 'CI/CD',
            percent: 90,
            image: 'gitlab-256x256.png',
            description: 'Maintaining proper private registry or jobs pipelines is a must-have.',
          },
        ],
        web: [
          {
            name: 'Symfony',
            percent: 95,
            image: 'symfony-256x256.png',
            description: 'A lot of my previous web works were done through Symfony',
          },
          {
            name: 'Vue',
            percent: 95,
            image: 'vue-200x200.png',
            description: 'This site is made in Vue. This is the only front framework I am confident with.',
          },
          {
            name: 'Angular',
            percent: 60,
            image: 'angular-256x256.webp',
            description: 'I used to made several front apps using Angular (even in older angular.js).',
          },
          {
            name: 'React-Native',
            percent: 40,
            image: 'react-256x256.png',
            description: 'I have some bases in mobile cross-platform development through this framework.',
          },
        ],
        other: [
          {
            name: 'Scrum Agility',
            percent: 90,
            image: 'atlassian-256x256.png',
            description: 'I also worked with Agility, using sprint and retros. I have been scrum master several times.',
          },
          {
            name: 'Music Production',
            percent: 50,
            image: 'ableton-256x256.png',
            description: 'I am passionate by music production (drum and bass mostly). I use Ableton as DAW.',
          },
        ],
      },
    };
  },
};
</script>

<style lang="scss" scoped>
.skills {
  margin-top: 40px;
}
</style>
