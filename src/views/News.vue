<template>
  <div>
    <v-btn @click="dohvatiNastavnike('tomislav')">Pretraži</v-btn>

    <v-container>
      <v-row>
        <v-col v-for="nastavnik in nastavnici" :key="nastavnik.id" cols="4">
          <v-card class="mx-auto" max-width="344" outlined>
            <v-list-item three-line>
              <v-list-item-content>
                <div class="overline mb-4">{{ nastavnik.sastavnica }}</div>
                <v-list-item-title class="headline mb-1">
                  {{ nastavnik.ime + " " + nastavnik.prezime }}
                </v-list-item-title>
                <v-list-item-subtitle
                  >{{ nastavnik.aai_kor_ime }}@sum.ba</v-list-item-subtitle
                >
              </v-list-item-content>

              <v-list-item-avatar
                tile
                size="80"
                color="grey"
              ></v-list-item-avatar>
            </v-list-item>

            <v-card-actions>
              <v-btn outlined rounded text>Prikaži profil</v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "Profile",
  data: () => ({
    nastavnici: [],
  }),
  created() {
    this.dohvatiNastavnike("ivan");
  },
  methods: {
    dohvatiNastavnike: function (ime) {
      this.axios
        .get("https://api.sum.ba/nastavnici?page=1&sastavnica=5&search=" + ime)
        .then((response) => {
          this.nastavnici = response.data.data;
        });
    },
  },
};
</script>
