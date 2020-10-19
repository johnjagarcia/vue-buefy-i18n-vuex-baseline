<template>
  <div class="home">
    <p>{{ count }}</p>
    <div class="buttons is-centered">
      <b-button type="is-success is-light" @click="increment">
        {{ $t("modules.counter.increment") }}
      </b-button>

      <b-button type="is-danger is-light" @click="decrement">
        {{ $t("modules.counter.decrement") }}
      </b-button>
    </div>
  </div>
</template>

<script>
import { mapState } from "vuex";

export default {
  name: "Home",
  components: {},
  computed: mapState({
    count: (state) => state.counter.count,
  }),
  methods: {
    increment() {
      this.$store.commit("counter/increment");
    },
    decrement() {
      this.$store.commit("counter/decrement");
    },
  },
};
</script>
