<template>
  <v-content class="mx-4">
    <div class="home">
      <Navbar />
      <h1 class="subheading grey--text">Home</h1>
      <v-container class="my-5 white">
        <v-layout row class="mb-3">
          <v-tooltip top>
            <template v-slot:activator="{ on }">
              <v-btn small text color="grey" v-on="on" @click="sortBy('title')">
                <v-icon left small>mdi-folder</v-icon>
                <span class="caption text-lowercase">by project name</span>
              </v-btn>
            </template>
            <span>Sort projects by title</span>
          </v-tooltip>
          <v-tooltip top>
            <template v-slot:activator="{ on }">
              <v-btn
                small
                text
                color="grey"
                v-on="on"
                @click="sortBy('person')"
              >
                <v-icon left small>mdi-account</v-icon>
                <span class="caption text-lowercase">by person</span>
              </v-btn>
            </template>
            <span>Sort projects by person</span>
          </v-tooltip>
        </v-layout>
        <v-card flat v-for="project in projects" :key="project.title">
          <v-layout row wrap :class="`pa-3 project ${project.status}`">
            <v-flex xs12 md6>
              <div class="caption grey--text">Project title</div>
              <div>{{ project.title }}</div>
            </v-flex>
            <v-flex xs6 sm4 md2>
              <div class="caption grey--text">Person</div>
              <div>{{ project.person }}</div>
            </v-flex>
            <v-flex xs6 sm4 md2>
              <div class="caption grey--text">Due by</div>
              <div>{{ project.due }}</div>
            </v-flex>
            <v-flex xs6 sm4 md2>
              <!-- <div class="caption grey--text">Status</div>
            <div>{{project.status}}</div> -->
              <div class="float-sm-right">
                <v-chip
                  small
                  :class="`${project.status} white--text caption my-4`"
                  >{{ project.status }}</v-chip
                >
              </div>
            </v-flex>
          </v-layout>
          <v-divider></v-divider>
        </v-card>
      </v-container>
    </div>
  </v-content>
</template>

<script>
import Navbar from '@/components/Navbar';
export default {
  name: 'Dashboard',
  components: { Navbar },
  data() {
    return {
      projects: [
        {
          title: 'Design a new website',
          person: 'The Net ninja',
          due: '1st of March 2020',
          status: 'complete',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tenetur et consectetur rem veritatis quibusdam, itaque molestias nihil maiores hic ut? Atque non ad libero minus vel. Porro eos veniam sapiente.'
        },
        {
          title: 'Code up homepage',
          person: 'Chun Li',
          due: '18th March 2020',
          status: 'ongoing',
          content:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni, distinctio quasi. Commodi hic dolores a iure ipsam aliquid exercitationem corrupti, autem nemo corporis quos placeat sapiente earum. Praesentium, repellat quo.'
        },
        {
          title: 'Design Video Thumbnails',
          person: 'Ryu',
          due: '28th April 2020',
          status: 'ongoing',
          content:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Corporis natus cupiditate beatae rem, ut ab. Possimus, animi quas officiis voluptas corporis consectetur magnam omnis impedit consequuntur odit id cumque dolores.'
        },
        {
          title: 'Create a Community forum',
          person: 'Gouken',
          due: '20th Dec 2020',
          status: 'ongoing',
          content:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Numquam, quibusdam debitis quaerat corporis dignissimos quae hic recusandae quas, enim, voluptate possimus eveniet doloremque ex earum dicta odit eligendi totam repellendus.'
        },
        {
          title: 'Design a portfolio',
          person: 'The Net ninja',
          due: '13th Sept 2019',
          status: 'overdue',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tenetur et consectetur rem veritatis quibusdam, itaque molestias nihil maiores hic ut? Atque non ad libero minus vel. Porro eos veniam sapiente.'
        }
      ]
    };
  },
  methods: {
    sortBy(prop) {
      this.projects.sort((a, b) => (a[prop] < b[prop] ? -1 : 1));
    }
  }
};
</script>
<style scoped>
.project.complete {
  border-left: 4px solid #3cd1c2;
}
.project.ongoing {
  border-left: 4px solid orange;
}
.project.overdue {
  border-left: 4px solid tomato;
}
.theme--light.v-chip.complete {
  background: #3cd1c2;
}
.theme--light.v-chip.ongoing {
  background: orange;
}
.theme--light.v-chip.overdue {
  background: tomato;
}
</style>
