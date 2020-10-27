<template>
  <div class="d-flex">
    <v-container>
      <v-row class="my-16 justify-center">
        <div class="case">
          <v-text-field
            label="shenk-am"
            outlined
            placeholder="http://example.com"
            class="tf mt-16"
            color="#6C63FF"
            append-outer-icon="mdi-gesture-double-tap"
            @click:append-outer="shenkAm"
            v-model="longLink"
          ></v-text-field>
          <v-expand-transition>
            <v-alert
              prominent
              text
              color="#6C63FF"
              :value="alert"
              transition="expand-transition"
            >
              {{ shortLink }}
            </v-alert>
          </v-expand-transition>
        </div>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      shortLink: '',
      longLink: '',
      alert: false,
      expand: false,
    }
  },
  methods: {
    async shenkAm() {
      try {
        const ip = await this.$axios.$post(
          'https://shenkess.herokuapp.com/shenkam',
          {
            longUrl: this.longLink,
          }
        )
        // console.log(ip.shortUrl)
        this.expand = true
        this.alert = true
        this.shortLink = ip.shortUrl
      } catch (error) {
        console.log(error)
      }
    },
  },
}
</script>

<style scoped>
.bg {
  background: #ecf4ff;
  clip-path: polygon(
    50% 0%,
    100% 0,
    100% 43%,
    94% 78%,
    68% 100%,
    32% 100%,
    0 100%,
    0% 43%,
    17% 12%
  );
}
.ro {
  height: 50hv;
}

.tf {
  border-radius: 10px;
}

.case {
  width: 500px;
}
</style>
