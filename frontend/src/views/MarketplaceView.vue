<template>
    <SearchBar />
    <v-row>
        <v-col
          cols="12"
          xs="12"
          sm="6"
          md="4"
          lg="3"
          v-for="(workflow, i) in workflows"
          :key="i"
        >
          <v-card
            class="mx-auto my-12 rounded-xl"
            max-width="374"
            color="grey"
          >
            <v-img height="170" :src="workflow.image"></v-img>
            <v-toolbar color="transparent" class="mt-n7" flat>
              <v-spacer></v-spacer>
              <v-avatar color="black" rounded class="mr-2" dark>
                <div class="three">
                  <div class="four">
                    <span class>{{ workflow.rating }}</span>
                  </div>
                  <div class="five">
                    <v-icon icon="mdi-star"></v-icon>
                  </div>
                </div>
              </v-avatar>
            </v-toolbar>
            <v-card-title class="grey--text caption">{{
              workflow.category
            }}</v-card-title>

            <v-card-text class="mt-n4">
              <v-chip-group
                active-class="deep-purple accent-4 white--text"
                column
              >
                <v-btn class="pink white--text">Download</v-btn>
                <v-spacer></v-spacer>
                <v-avatar size="40">
                  <v-img :src="workflow.avatar"></v-img>
                </v-avatar>
              </v-chip-group>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
</template>

<script>
import SearchBar from '@/components/SearchBar.vue'
export default {
  name: 'Marketplace',
  components : {SearchBar},
  data: () => ({
    workflows: [
      {
        image: "aerospace.jpg",
        rating: "5",
        category: "category: Aerospace",
        avatar: "https://cdn.vuetifyjs.com/images/lists/1.jpg",
      },
      {
        image: "healthcare.jpg",
        rating: "4",
        category: "category: Healthcare",
        avatar: "https://cdn.vuetifyjs.com/images/lists/2.jpg",
      },
      {
        image: "mining.jpg",
        rating: "5",
        category: "category: Mining",
        avatar: "https://cdn.vuetifyjs.com/images/lists/3.jpg",
      },
      {
        image: "paralegal.jpg",
        rating: "4",
        category: "category: Paralegal",
        avatar: "https://cdn.vuetifyjs.com/images/lists/4.jpg",
      },
    ]
  }),
}
</script>