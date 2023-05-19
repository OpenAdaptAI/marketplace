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
            max-width="300"
            color="grey"
          >
            <v-img width = "300" height="155" :src="workflow.image" cover></v-img>
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
            }} Workflow </v-card-title>
          <v-card-text>
            {{ workflow.name }}
          </v-card-text>
          <v-card-text size="small">
            {{ workflow.description }}
          </v-card-text>
            <v-card-text class="mt-n4">
              <v-chip-group
                active-class="deep-purple accent-4 white--text"
                column
              >
                <v-btn color="black">Download</v-btn>
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
        name: "Quality Assurance Compliance",
        image: "aerospace.jpg",
        rating: "5",
        category: "Aerospace",
        avatar: "https://cdn.vuetifyjs.com/images/lists/1.jpg",
        description : "This workflow focuses on automating quality assurance processes in aerospace manufacturing, ensuring compliance with industry standards and regulations. It involves automatically inspecting and validating components, tracking and documenting inspections, and generating compliance reports.",
      },
      {
        name : "Patient Onboarding and Registration",
        image: "healthcare.jpg",
        rating: "4",
        category: "Healthcare",
        avatar: "https://cdn.vuetifyjs.com/images/lists/2.jpg",
        description : "This workflow streamlines the patient onboarding and registration process in healthcare institutions. It involves automating the collection and verification of patient information, verifying insurance details, scheduling appointments, and generating digital patient records."
      },
      {
        name : "Safety Incident Reporting",
        image: "mining.jpg",
        rating: "5",
        category: "Mining",
        avatar: "https://cdn.vuetifyjs.com/images/lists/3.jpg",
        description : "This workflow automates the reporting and tracking of safety incidents in the mining industry. It includes capturing incident details, notifying relevant stakeholders, initiating investigations, and generating incident reports for compliance and analysis purposes."
      },
      {
        name : "Legal Document Review and Analysis",
        image: "paralegal.jpg",
        rating: "4",
        category: "Paralegal",
        avatar: "https://cdn.vuetifyjs.com/images/lists/4.jpg",
        description : "This workflow facilitates the review and analysis of legal documents by automating the process for paralegal professionals. It involves automatically extracting key information from documents, conducting legal research, identifying relevant precedents, and generating summaries or recommendations for attorneys."
      },
    ]
  }),
}
</script>