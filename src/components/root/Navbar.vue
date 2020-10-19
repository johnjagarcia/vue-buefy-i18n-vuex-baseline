<template>
  <b-navbar>
    <template slot="brand">
      <b-navbar-item tag="router-link" :to="{ path: '/' }">
        <img
          src="https://raw.githubusercontent.com/buefy/buefy/dev/static/img/buefy-logo.png"
          alt="Lightweight UI components for Vue.js based on Bulma"
        />
      </b-navbar-item>
    </template>
    <template slot="start">
      <b-navbar-item tag="router-link" :to="{ path: '/' }">
        {{ $t("general.home") }}
      </b-navbar-item>
      <b-navbar-item tag="router-link" :to="{ path: '/about' }">
        {{ $t("general.about") }}
      </b-navbar-item>
    </template>

    <template slot="end">
      <b-navbar-item tag="div">
        <b-dropdown v-model="lang" aria-role="list">
          <button class="button is-fullwidth" type="button" slot="trigger">
            <span>{{ ` ${lang.name}` }}</span>
            <b-icon icon="menu-down"></b-icon>
          </button>

          <b-dropdown-item
            v-for="lang in langs"
            :key="lang.id"
            :value="lang"
            aria-role="listitem"
          >
            <span>{{ ` ${lang.name}` }}</span>
          </b-dropdown-item>
        </b-dropdown>
      </b-navbar-item>
    </template>
  </b-navbar>
</template>

<script>
export default {
  data() {
    return {
      langs: [
        { id: 1, code: "en", name: "English" },
        { id: 2, code: "es", name: "Español" },
      ],
      lang: { id: 2, code: "es", name: "Español" },
    };
  },
  watch: {
    lang() {
      this.$i18n.locale = this.lang.code;
    },
  },
};
</script>