<template>
  <v-content class="m4">
    <div class="project">
      <Navbar />
      <h1 class="subheading grey--text">This is projects page</h1>
      <v-container class="my-5">
        <v-row justify="center">
          <v-expansion-panels>
            <v-expansion-panel
              v-for="project in myProjects"
              :key="project.title"
            >
              <v-expansion-panel-header>{{
                project.title
              }}</v-expansion-panel-header>
              <v-expansion-panel-content>
                <v-card flat>
                  <div class="font-weight-bold grey--text">
                    due by {{ project.due }}
                  </div>
                </v-card>
                {{ project.content }}
              </v-expansion-panel-content>
            </v-expansion-panel>
          </v-expansion-panels>
        </v-row>
      </v-container>
    </div>
  </v-content>
</template>
<script>
import Navbar from '@/components/Navbar';
export default {
  name: 'Project',
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
  computed: {
    myProjects() {
      return this.projects.filter(project => {
        let personal = project.person == 'The Net ninja';
        return personal;
      });
    }
  }
};
</script>
