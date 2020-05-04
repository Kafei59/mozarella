<template>
  <div>
    <p class="main-text">
      I worked a <strong>Software Engineer</strong> 💻
      since I graduated from Epitech computer science School.<br/>
      I started as a web developer using PHP frameworks before moving to software engineering.<br/>
      Now, I mainly work in <strong>Golang and Cloud</strong> ☁️ environments with a
      <strong>DevOps</strong> ⚙️ culture.<br/><br/>

      <router-link to="/">
        <el-button type="primary">Get me back to the main page ! 👋</el-button>
      </router-link>&nbsp;&nbsp;

      <router-link to="/skills">
        <el-button type="primary">This is cool but let see the skills ! ⚡️</el-button>
      </router-link>&nbsp;&nbsp;

      <router-link to="/contact">
        <el-button type="primary">Wow, where can we reach you ? 📩</el-button>
      </router-link>
    </p>

    <el-row :span="24">
      <el-col :lg="{span: 17, offset: 3}">
        <el-timeline class="resume">
          <el-timeline-item v-for="(experience, index) in experiences" :key="index"
                            placement="top" class="text-left"
                            :timestamp="experience.start + ' - ' + experience.end"
          >
            <template slot="dot">
              <el-avatar :src="GetImage(experience.image)" shape="square" :size="100" fit="fill"/>
            </template>

            <el-card class="card">
              <div slot="header" class="clearfix text-center card-title">
                <strong>{{ experience.company }}</strong> - {{ experience.job }}
              </div>

              <div class="card-body">
                <p>
                  <span v-for="(desc, index) in experience.description" :key="index">
                    {{ desc }}<br/>
                  </span>
                </p>
              </div>

              <div class="card-footer">
                <el-tag v-for="(tag, index) in experience.tags" :key="index" class="tag">
                  {{ tag }}
                </el-tag>

                <p>
                  <a v-bind:href="experience.link" target="_blank">{{ experience.link }}</a>
                </p>
              </div>
            </el-card>
          </el-timeline-item>
        </el-timeline>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: 'Resume',

  methods: {
    GetImage(img) {
      // eslint-disable-next-line global-require,import/no-dynamic-require
      return require(`../assets/companies/${img}`);
    },
  },

  data() {
    return {
      experiences: [
        {
          company: 'OVHcloud',
          job: 'Software Engineer',
          image: 'ovhcloud-316x316.jpg',
          link: 'https://www.linkedin.com/company/ovhgroup/',
          tags: ['golang', 'kubernetes', 'kafka', 'python', 'perl', 'vue'],
          start: 'November 2017',
          end: 'now',
          description: [
            'Currently, I am working in the Managed Kubernetes team.',
            'My work is to develop all new features and tools for ours customers Kubernetes clusters.',
            'The main codebase is written in Golang.',
            '',
            'I also worked with the shared hosting delivery team for about a year and a half',
            'During this time, I had plenty of occasions to deal with the huge OVH hosting services ecosystem.',
            'We dealt with a lot of issues to be able to host 1.5 millions customers.',
            'My main mission was to ensure the delivery of shared hosting offers, that means, '
            + 'between the moment a customer order an hosting, the period when the infrastructure '
            + 'is able to boot the virtual machine and respond back everything is OK.',
            'Everything was built on a legacy code source made with huge number of PERL scripts.',
            'I had the occasion to finally sell the Cloud Web offer which was in "sleep mode" '
            + 'for a few years. It was quite a challenge, to continue to handle the legacy code '
            + 'and insert some new fresh code made with some quite new technologies.',
          ],
        },
        {
          company: 'Pumpkin',
          job: 'Lead Web Developer',
          image: 'pumpkin-499x474.png',
          link: 'https://www.linkedin.com/company/pumpkin-app/',
          tags: ['symfony', 'mongoDB', 'postgreSQL', 'kafka', 'elasticsearch'],
          start: 'September 2015',
          end: 'October 2017',
          description: [
            'As a lead web developer, I had to handle several parts of Pumpkin web process.',
            '',
            'I launched some backend refactoring by using new tools (at that time):',
            '- Refactor not-so-fully REST Symfony2 application into a new brand Symfony3 REST API more microserved,',
            '- Launched an Angular2 project for the upcoming new version of the Event application,',
            '- Migrate mongodb into postgreSQL for more consistency,',
            '- Integrate Apache Kafka and Elasticsearch to optimize, as much as possible, every calls made onto the API to get faster responses.',
            '- Test driven development : functional tests with Behat and unit test with PHPUnit,',
            '- Implement payment systems (Mangopay) and other secured builtin (3DSecure, ...),',
            '- Create backend code architecture with multiple conception meetings',
            '',
            'I also had to manage 2 others senior developers in my team, all working together, and that helped me to discover new kinds of lead management methods.',
          ],
        },
        {
          company: 'Epitech',
          job: 'Learning Assistant',
          image: 'epitech-246x223.png',
          link: 'https://www.linkedin.com/company/epitech/',
          tags: ['c++', 'c', 'learning', 'support'],
          start: 'January 2015',
          end: 'August 2015',
          description: [
            'I was a support assistant for several months during my second year graduation at Epitech.',
            '',
            'This role was used to help freshmen to discover programming world as smooth as possible'
            + ' and even try to help students of my promotion to not discourage !',
            '',
            'Technically, it was support on C/C++ projects but I had the opportunity to discover the world of the group management '
            + 'by giving lessons to a bunch of students, get feedbacks and talk to them afterwise.',
          ],
        },
        {
          company: 'No Parking',
          job: 'Web Developer (internship)',
          image: 'noparking-200x200.png',
          link: 'https://www.linkedin.com/company/no-parking/',
          tags: ['php', 'jquery', 'AJAX', 'html', 'css'],
          start: 'June 2014',
          end: 'December 2014',
          description: [
            'I was a web backend developer using a homemade custom PHP framework on a cash management software.',
            '',
            'For the first time, I discover how the world of web development was working on a professional point of view.',
            'I had to work on some new stuff for me and understand new process:',
            '- How was working PHP in its deepest hideouts,',
            '- How was working a REST API,',
            '- What was the difference between a monolithic and a microserved application,',
            '- What was behind the word AJAX',
            '',
            'For a global understanding, it was mainly my first profesionnal experiences and I understand may more things about development that I could have thinked of !',
          ],
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.resume {
  margin-top: 20px;
}

.el-avatar {
  background: #f7f7f7;
  position: relative;
  left: -50px;
}

.el-timeline-item__wrapper {
  position: relative;
  left: 50px;

  .el-timeline-item__timestamp {
    position: relative;
    left: 20px;
  }
}

.card-footer {
  .tag {
    margin-right: 10px;
  }
}
</style>
