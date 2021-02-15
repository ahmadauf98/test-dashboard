<template>
  <div>
    <!-- Dashboard Nav -->
    <v-card class="pt-6 pb-5" color="#2d325a" flat tile dark>
      <v-row class="px-12">
        <v-col class="d-flex align-center">
          <img
            class="mr-3"
            src="~/static/players-icon.svg"
            width="35"
            alt="..."
          />
          <h1 class="text-h5">Players</h1>
        </v-col>

        <v-col class="d-flex justify-end align-center">
          <h1 class="text-h6 font-weight-bold">John Doe</h1>

          <v-avatar size="40" class="ml-3">
            <img src="~/static/img/avatar-default.svg" alt="..." />
          </v-avatar>
        </v-col>
      </v-row>

      <v-divider class="mt-4 mb-3" color="#1b1f3b" light></v-divider>

      <v-row class="px-12">
        <v-col class="d-flex align-center py-0">
          <h1 class="text-h6 font-weight-thin ml-3">200 Records</h1>
        </v-col>

        <v-col class="d-flex justify-end align-center py-0">
          <v-col>
            <v-btn class="text-h6 font-weight-thin text-capitalize" text>
              <img class="mr-3" src="~/static/sort-za-icon.svg" alt="..." />
              Sort</v-btn
            >
          </v-col>

          <v-col>
            <v-btn class="text-h6 font-weight-thin text-capitalize" text>
              <img class="mr-3" src="~/static/export-icon.svg" alt="..." />
              Export<span class="text-lowercase mx-1">to</span>Excel</v-btn
            >
          </v-col>

          <v-col cols="7" class="pa-0">
            <v-text-field
              background-color="#1b1f3b"
              class="mb-n8 custom-placeholer-color py-3"
              placeholder="Search"
              dense
              filled
              rounded
            >
              <template v-slot:prepend-inner>
                <img
                  class="ml-n1 mr-3 mt-0 mb-2"
                  width="23"
                  height="23"
                  src="~/static/search-icon.svg"
                />
              </template>
            </v-text-field>
          </v-col>
        </v-col>
      </v-row>
    </v-card>

    <!-- Dashboard Content -->
    <v-card
      class="mt-10 ml-15 mr-12"
      height="720"
      color="#2d325a"
      rounded="lg"
      flat
      dark
    >
      <v-card class="d-flex align-center" color="#2d325a" height="90" flat>
        <v-row>
          <v-col
            v-for="(tableHeader, index) in tableHeaders"
            :key="index"
            class="d-flex justify-center"
          >
            <img
              class="mr-1"
              width="13"
              src="~/static/sort-za-icon-grey.svg"
              alt="..."
            />

            <h1 class="text-h6 font-weight-medium">{{ tableHeader }}</h1>
          </v-col>
        </v-row>
      </v-card>

      <v-divider color="#1b1f3b" light></v-divider>

      <v-card
        v-for="(tableContent, index) in tableContents"
        :key="index"
        class="my-3"
        color="#2d325a"
        flat
        tile
      >
        <v-row class="d-flex align-self-center py-2">
          <v-col class="d-flex justify-center align-center">
            <h1 class="text-h6 font-weight-thin">{{ tableContent.no }}</h1>
          </v-col>
          <v-col class="d-flex justify-center align-center">
            <v-avatar size="40" class="ml-3">
              <img :src="tableContent.profilePic" alt="..." />
            </v-avatar>
          </v-col>
          <v-col class="d-flex justify-center align-center">
            <h1 class="text-h6 font-weight-thin">
              {{ tableContent.fullName }}
            </h1>
          </v-col>
          <v-col class="d-flex justify-center align-center">
            <h1 class="text-h6 font-weight-thin">
              {{ tableContent.email }}
            </h1>
          </v-col>
          <v-col class="d-flex justify-center align-center">
            <h1 class="text-h6 font-weight-thin">
              {{ tableContent.country }}
            </h1>
          </v-col>
          <v-col class="d-flex justify-center align-center">
            <h1 class="text-h6 font-weight-thin">
              {{ tableContent.highScore }}
            </h1>
          </v-col>
        </v-row>

        <v-row class="ml-15">
          <v-divider
            v-show="index < 5"
            class="ml-10"
            color="#1b1f3b"
            light
          ></v-divider>
        </v-row>
      </v-card>

      <v-card class="my-10" color="#2d325a" height="70" flat tile>
        <v-row>
          <v-col class="ml-15 pl-13">
            <v-btn
              class="text-subtitle-1 font-weight-thin text-capitalize"
              color="#1b1f3b"
              large
              depressed
              tile
            >
              Showing Entries : 10
              <img class="ml-3" src="~/static/dropdown-icon.svg" alt="..." />
            </v-btn>
          </v-col>

          <v-col class="d-flex justify-end mr-13">
            <v-pagination
              class="custom-pagination text-subtitle-1 font-weight-thin"
              v-model="page"
              :length="4"
            ></v-pagination>
          </v-col>
        </v-row>
      </v-card>
    </v-card>
  </div>
</template>

<script>
import searchIcon from '~/static/search-icon.svg'

export default {
  components: {
    searchIcon,
  },

  data() {
    return {
      tableHeaders: [
        'S/N',
        'Profile Pic',
        'Full Name',
        'Email',
        'Country',
        'High Score',
      ],

      tableContents: [
        {
          no: '01',
          profilePic: 'profile.svg',
          fullName: 'John Doe ',
          email: 'John@xyz.com',
          country: 'Nigeria',
          highScore: '500',
        },
        {
          no: '01',
          profilePic: 'profile.svg',
          fullName: 'John Doe ',
          email: 'John@xyz.com',
          country: 'Nigeria',
          highScore: '300',
        },
        {
          no: '01',
          profilePic: 'profile.svg',
          fullName: 'John Doe ',
          email: 'John@xyz.com',
          country: 'Nigeria',
          highScore: '350',
        },
        {
          no: '01',
          profilePic: 'profile.svg',
          fullName: 'John Doe ',
          email: 'John@xyz.com',
          country: 'Nigeria',
          highScore: '330',
        },
        {
          no: '01',
          profilePic: 'profile.svg',
          fullName: 'John Doe ',
          email: 'John@xyz.com',
          country: 'Nigeria',
          highScore: '320',
        },
        {
          no: '01',
          profilePic: 'profile.svg',
          fullName: 'John Doe ',
          email: 'John@xyz.com',
          country: 'Nigeria',
          highScore: '310',
        },
      ],

      page: 1,
    }
  },
}
</script>
