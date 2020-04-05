<template>
  <v-content class="mx-4">
    <div class="team">
      <Navbar />
      <h1 class="subheading grey--text">This is Team Page</h1>
      <v-container class="my-5">
        <v-layout row wrap>
          <v-flex xs12 sm6 md4 lg3 v-for="person in team" :key="person.name">
            <v-card flat class="text-center ma-3">
              <v-img class="pt-4">
                <v-avatar size="100" class="grey lighten-2">
                  <img :src="person.avatar" />
                </v-avatar>
              </v-img>
              <v-card-text>
                <div class="subheading">{{ person.name }}</div>
                <div class="grey--text">{{ person.role }}</div>
              </v-card-text>
              <v-card-actions>
                <v-btn text color="grey">
                  <v-icon small left>mdi-message-bulleted</v-icon>
                  <span>Message</span>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </div>
  </v-content>
</template>

<script>
import Navbar from '@/components/Navbar';
export default {
  name: 'Team',
  components: { Navbar },
  data() {
    return {
      team: [
        {
          name: 'The Net Ninja',
          role: 'Web developer',
          avatar: '/avatar-1.png'
        },
        { name: 'Ryu', role: 'Graphic designer', avatar: '/avatar-2.png' },
        { name: 'Chun li', role: 'Web developer', avatar: '/avatar-3.png' },
        {
          name: 'Goken',
          role: 'Social media naverick',
          avatar: '/avatar-4.png'
        },
        { name: 'Yoshi', role: 'Sales guru', avatar: '/avatar-5.png' }
      ]
    };
  }
};
</script>
