<template>
  <div class="sect">
    <v-row justify="center" align="center">
      <v-col cols="12" sm="8" md="6">
        <v-container>
          <div>
            <p class="text-center text-capitalize text pt-4">Vibes and <span class="subtext">inshallah /ɪnˈʃalə/</span></p>
          </div>
          <div class="mt-16 bg" >
             <img src="/share_link.svg?inline">
           <!-- <img src="/share_link.svg" /> -->
          </div>
        </v-container>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  components: {},
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap');
.bg{
  background: #ECF4FF;
  clip-path: polygon(50% 0%, 100% 0, 100% 43%, 94% 78%, 68% 100%, 32% 100%, 0 100%, 0% 43%, 17% 12%);
}

.text{
  font-family: 'Poppins', sans-serif;
  font-size: 40px;
}

.subtext{
  color: #6C63FF;
}

</style>
