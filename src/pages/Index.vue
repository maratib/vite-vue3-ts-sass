<script lang="ts">
import { useI18n } from 'vue-i18n';

import { defineComponent, ref } from 'vue';
import { useTheme } from '/@/composables';

export default defineComponent({
  name: 'Home',
  setup() {
    const { t, availableLocales, locale } = useI18n();

    const toggleLocales = () => {
      const locales = availableLocales;
      locale.value =
        locales[(locales.indexOf(locale.value) + 1) % locales.length];
    };

    const { isDark, toggleDark } = useTheme();

    const show = ref(false);

    setTimeout(() => {
      show.value = true;
    }, 1000);

    return { locale, t, show, toggleLocales, isDark, toggleDark };
  },
});
</script>

<template>
  <div class="hi">
    <HelloWorld class="bye" :msg="t('hello') + ' 👋 !!'" />
  </div>
</template>

<style scoped lang="scss">
.hi {
  background: green;
  padding: 2em;
  .bye {
    background: blue;
  }
}
</style>
