<template>
  <app-layout>
    <template #header>
      <h2 class="text-xl font-semibold leading-tight text-gray-800">
        Módulo de Notas
      </h2>
    </template>

    <div class="py-12">
      <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
        <div class="md:grid md:grid-cols-3 md:gap-6">
          <div class="md:col-span-1">
            <div class="px-4 sm:px0">
              <h3 class="text-lg text-gray-900">Detalle de una nota</h3>
              <p class="text-sm text-gray-600">{{ note.excerpt }}</p>
            </div>
          </div>
          <div class="mt-5 md:col-span-2 md:mt-0">
            <div class="p-4 bg-white shadow md:rounded-md">
              <p>{{ note.content }}</p>

              <hr class="my-6" />

              <inertia-link :href="route('notes.index')"> Volver </inertia-link>
            </div>
          </div>
        </div>
      </div>
    </div>
  </app-layout>
</template>

<script>
import AppLayout from "@/Layouts/AppLayout";

export default {
  components: {
    AppLayout,
  },
  props: {
    note: Object,
  },
};
</script>
