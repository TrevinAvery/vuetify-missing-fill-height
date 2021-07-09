<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />
      </div>
    </v-app-bar>

    <v-main>
      <v-row>
				<v-col v-for="n in 9" :key="n" class="d-flex child-flex" cols="4">
					<v-img
						:src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
						:lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}`"
						aspect-ratio="1"
						class="grey lighten-2"
					>
						<template v-slot:placeholder>
							<v-row class="fill-height ma-0" align="center" justify="center">
								<v-progress-circular
									indeterminate
									color="grey lighten-5"
								></v-progress-circular>
							</v-row>
						</template>
					</v-img>
				</v-col>
			</v-row>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  data: () => ({
    //
  }),
};
</script>
