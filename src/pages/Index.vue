<script setup lang="ts">
import { darkTheme } from "naive-ui";
const { t, locale } = useI18n();
const { isDark, toggleDark } = useDarks();

const theme = ref(null);
const toggleLocale = () => {
  locale.value = locale.value === "zh-CN" ? "en" : "zh-CN";
};
</script>

<template>
  <n-config-provider :theme="theme">
    <n-card>
      <div class="m-6">{{ t("Hello, This is the tov template") }}！！</div>
      <n-button class="cursor-pointer m-6" @click="toggleDark()">
        tov {{ t("light") }}: {{ isDark }} {{ t("click me") }}!!
      </n-button>
      <br />
      <n-button class="cursor-pointer m-6" @click="toggleLocale()">
        <i-mdi:hammer-sickle />
        {{ t("language") }}: {{ t("index") }} {{ t("click me") }}!!
      </n-button>
      <br />
      <n-button
        type="primary"
        class="cursor-pointer m-6"
        @click="theme = darkTheme"
      >
        {{ t("dark") }}
      </n-button>
      <n-button type="info" class="cursor-pointer m-6" @click="theme = null">
        {{ t("light") }}
      </n-button>
    </n-card>
  </n-config-provider>
</template>
