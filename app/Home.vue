<template>
  <Page>
    <ActionBar title="Travel App Starter (Vue 3)" />

    <StackLayout class="page" spacing="12" padding="24">
      <Label text="Willkommen bei deiner ersten NativeScript Vue 3 App!" textWrap="true" class="h2" />
      <Label text="Tippe auf den Button, um den Counter zu erhöhen." textWrap="true" />

      <Button text="Klick mich" class="btn btn-primary" @tap="increment" />
      <Label :text="message" textWrap="true" class="h3" />
    </StackLayout>
  </Page>
</template>

<script setup lang="ts">
import { computed, ref } from "vue";

const count = ref(0);

const message = computed(() =>
  count.value === 0 ? "Du hast noch nicht geklickt." : `Du hast ${count.value} Mal geklickt.`
);

const increment = (): void => {
  count.value += 1;
};
</script>

<style scoped>
.page {
  background-color: #f8fafc;
}
</style>
