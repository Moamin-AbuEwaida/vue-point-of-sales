<template>
  <v-app :style="{ background: $vuetify.theme.themes.dark.background }">
    <SideBar />
    <NavBar />
    <v-container fluid>
      <v-app-bar dark color="transparent" flat>
        <v-tabs color="#f34f64" v-model="tab">
          <v-tabs-slider color="#f34f64"></v-tabs-slider>
          <v-tab class="withoutupercase">Parasut</v-tab>
          <v-tab class="withoutupercase">Parka</v-tab>
          <v-tab class="withoutupercase">Steve</v-tab>
          <v-tab class="withoutupercase">Dennis</v-tab>
        </v-tabs>
      </v-app-bar>
      <v-card tile color="#323b50" class="my-2 card_global">
        <v-row>
          <v-col cols="12" sm="8">
            <v-tabs-items v-model="tab">
              <v-tab-item>
                <v-card flat class="card_item pa-2">
                  <v-row>
                    <v-col
                      cols="12"
                      sm="3"
                      v-for="(parasut, i) in parasuts"
                      :key="i"
                    >
                      <v-hover v-slot="{ hover }" close-delay="200">
                        <v-card
                          :elevation="hover ? 16 : 2"
                          :class="{ 'on-hover': hover }"
                          class="mx-auto"
                          height="250"
                          tile
                          color="#333c51"
                          align="center"
                        >
                          <v-card-actions>
                            <v-spacer></v-spacer>
                            <v-btn
                              tile
                              small
                              :color="hover ? '#f34f64' : '#777d88'"
                              dark
                            >
                              {{ parasut.prix }}
                            </v-btn>
                          </v-card-actions>
                          <v-img
                            :src="parasut.avatar"
                            width="150"
                            height="150"
                          ></v-img>
                          <v-card-text
                            :class="hover ? 'red--text' : 'white--text'"
                          >
                            {{ parasut.title }}
                          </v-card-text>
                        </v-card>
                      </v-hover>
                    </v-col>
                  </v-row>
                </v-card>
              </v-tab-item>
              <v-tab-item>
                <v-card flat class="card_item pa-2">
                  <v-row>
                    <v-col
                      cols="12"
                      sm="3"
                      v-for="(parka, i) in parkas"
                      :key="i"
                    >
                      <v-hover v-slot="{ hover }" close-delay="200">
                        <v-card
                          :elevation="hover ? 16 : 2"
                          :class="{ 'on-hover': hover }"
                          class="mx-auto"
                          height="250"
                          tile
                          color="#333c51"
                          align="center"
                        >
                          <v-card-actions>
                            <v-spacer></v-spacer>
                            <v-btn
                              tile
                              small
                              :color="hover ? '#f34f64' : '#777d88'"
                              dark
                            >
                              {{ parka.prix }}
                            </v-btn>
                          </v-card-actions>
                          <v-img
                            :src="parka.avatar"
                            width="150"
                            height="150"
                          ></v-img>
                          <v-card-text
                            :class="hover ? 'red--text' : 'white--text'"
                          >
                            {{ parka.title }}
                          </v-card-text>
                        </v-card>
                      </v-hover>
                    </v-col>
                  </v-row>
                </v-card>
              </v-tab-item>
              <v-tab-item>
                <v-card flat class="card_item pa-2">
                  <v-row>
                    <v-col
                      cols="12"
                      sm="3"
                      v-for="(steve, i) in steves"
                      :key="i"
                    >
                      <v-hover v-slot="{ hover }" close-delay="200">
                        <v-card
                          :elevation="hover ? 16 : 2"
                          :class="{ 'on-hover': hover }"
                          class="mx-auto"
                          height="250"
                          tile
                          color="#333c51"
                          align="center"
                        >
                          <v-card-actions>
                            <v-spacer></v-spacer>
                            <v-btn
                              tile
                              small
                              :color="hover ? '#f34f64' : '#777d88'"
                              dark
                            >
                              {{ steve.prix }}
                            </v-btn>
                          </v-card-actions>
                          <v-img
                            :src="steve.avatar"
                            width="150"
                            height="150"
                          ></v-img>
                          <v-card-text
                            :class="hover ? 'red--text' : 'white--text'"
                          >
                            {{ steve.title }}
                          </v-card-text>
                        </v-card>
                      </v-hover>
                    </v-col>
                  </v-row>
                </v-card>
              </v-tab-item>
              <v-tab-item>
                <v-card flat class="card_item pa-2">
                  <v-row>
                    <v-col
                      cols="12"
                      sm="3"
                      v-for="(Dennis, i) in Dennises"
                      :key="i"
                    >
                      <v-hover v-slot="{ hover }" close-delay="200">
                        <v-card
                          :elevation="hover ? 16 : 2"
                          :class="{ 'on-hover': hover }"
                          class="mx-auto"
                          height="250"
                          tile
                          color="#333c51"
                          align="center"
                        >
                          <v-card-actions>
                            <v-spacer></v-spacer>
                            <v-btn
                              tile
                              small
                              :color="hover ? '#f34f64' : '#777d88'"
                              dark
                            >
                              {{ Dennis.prix }}
                            </v-btn>
                          </v-card-actions>
                          <v-img
                            :src="Dennis.avatar"
                            width="150"
                            height="150"
                          ></v-img>
                          <v-card-text
                            :class="hover ? 'red--text' : 'white--text'"
                          >
                            {{ Dennis.title }}
                          </v-card-text>
                        </v-card>
                      </v-hover>
                    </v-col>
                  </v-row>
                </v-card>
              </v-tab-item>
            </v-tabs-items>
          </v-col>
          <v-col cols="12" sm="4"> </v-col>
        </v-row>
      </v-card>
    </v-container>
  </v-app>
</template>

<script>
import SideBar from "@/components/SideBar.vue";
import NavBar from "@/components/NavBar.vue";
export default {
  name: "HomePage",
  data: () => ({
    tab: null,
    parasuts: [
      {
        avatar: "p1.jpeg",
        prix: "€40",
        title: "Style one Parasut",
      },
      {
        avatar: "p2.webp",
        prix: "€20",
        title: "Style two Parasut",
      },
      {
        avatar: "p3.jpeg",
        prix: "€50",
        title: "Style three Parasut",
      },
      {
        avatar: "p4.jpeg",
        prix: "€65",
        title: "Style four Parasut",
      },
      {
        avatar: "p5.jpeg",
        prix: "€40",
        title: "Style five Parasut",
      },
      {
        avatar: "p6.jpeg",
        prix: "€140",
        title: "Style six Parasut",
      },
      {
        avatar: "p7.webp",
        prix: "€90",
        title: "Style seven Parasut",
      },
      {
        avatar: "p8.jpeg",
        prix: "€20",
        title: "Style eight Parasut",
      },
    ],
    parkas: [
      {
        avatar: "r1.jpeg",
        prix: "€40",
        title: "Style one  Rain Jacket",
      },
      {
        avatar: "r2.jpeg",
        prix: "€20",
        title: "Style two  Rain Jacket",
      },
      {
        avatar: "r3.jpeg",
        prix: "€50",
        title: "Style three Rain Jacket",
      },
      {
        avatar: "r4.jpeg",
        prix: "€65",
        title: "Style four Rain Jacket",
      },
      {
        avatar: "r5.jpeg",
        prix: "€40",
        title: "Style five Rain Jacket",
      },
      {
        avatar: "r6.jpeg",
        prix: "€140",
        title: "Style six  Rain Jacket",
      },
      {
        avatar: "r7.jpeg",
        prix: "€90",
        title: "Style seven Rain Jacket",
      },
      {
        avatar: "r8.jpeg",
        prix: "€20",
        title: "Style eight Rain Jacket",
      },
    ],
    Dennises: [
      {
        avatar: "d1.jpeg",
        prix: "€40",
        title: "Style one Jeans Jacket",
      },
      {
        avatar: "d2.jpeg",
        prix: "€20",
        title: "Style two Jeans Jacket",
      },
      {
        avatar: "d3.jpeg",
        prix: "€50",
        title: "Style three Jeans Jacket",
      },
      {
        avatar: "d4.jpeg",
        prix: "€65",
        title: "Style four Jeans Jacket",
      },
      {
        avatar: "d5.jpeg",
        prix: "€40",
        title: "Style five Jeans Jacket",
      },
      {
        avatar: "d6.jpeg",
        prix: "€140",
        title: "Style six Jeans Jacket",
      },
      {
        avatar: "d7.jpeg",
        prix: "€90",
        title: "Style seven Jeans Jacket",
      },
      {
        avatar: "d8.jpeg",
        prix: "€20",
        title: "Style eight Jeans Jacket",
      },
    ],
    steves: [
      {
        avatar: "s1.jpeg",
        prix: "€40",
        title: "Style one Jacket",
      },
      {
        avatar: "s2.jpeg",
        prix: "€20",
        title: "Style two Jacket",
      },
      {
        avatar: "s3.jpeg",
        prix: "€50",
        title: "Style three Jacket",
      },
      {
        avatar: "s4.jpeg",
        prix: "€65",
        title: "Style four Jacket",
      },
      {
        avatar: "s5.jpeg",
        prix: "€40",
        title: "Style five Jacket",
      },
      {
        avatar: "s6.jpeg",
        prix: "€140",
        title: "Style six Jacket",
      },
      {
        avatar: "s7.jpeg",
        prix: "€90",
        title: "Style seven Jacket",
      },
      {
        avatar: "s8.jpeg",
        prix: "€20",
        title: "Style eight Jacket",
      },
    ],
  }),

  components: {
    SideBar,
    NavBar,
  },
};
</script>
<style scoped>
.v-tabs-slider {
  position: absolute;
  top: 30%;
  left: 50%;
  transform: translate(-50%, -50%);
  height: 15px !important;
  width: 20px !important;
  border-radius: 150px 150px 0px 0px;
  background-color: #f34f64;
}
.v-tab-withoutupercase {
  text-transform: none !important;
}
.v-tabs {
  width: 30% !important;
}
.container {
  padding: 0px !important;
}
.v-card.card_global {
  height: 800px !important;
}
.theme--light.v-card.card_item {
  background-color: #323850;
  color: #babec9 !important;
}
.v-sheet.v-card.card_item {
  border-radius: 0px !important;
}
.v-btn:not(.v-btn--round).v-size--small {
  width: 50px !important;
}
.v-application .red--text {
  color: #f34f64 !important;
  caret-color: #f34f64 !important;
}
</style>
