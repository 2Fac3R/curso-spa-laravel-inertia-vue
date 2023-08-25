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
              <h3 class="text-lg text-gray-900">Crear una nota</h3>
              <p class="text-sm text-gray-600">
                Luego de crear la podrás editar
              </p>
            </div>
          </div>
          <div class="mt-5 md:col-span-2 md:mt-0">
            <div class="p-4 bg-white shadow md:rounded-md">
              <form @submit.prevent="submit">
                <label class="block text-sm font-medium text-gray-700">
                  Resumen
                </label>
                <textarea
                  class="w-full rounded-md shadow-sm form-input"
                  v-model="form.excerpt"
                ></textarea>
                <label class="block text-sm font-medium text-gray-700">
                  Contenido
                </label>
                <textarea
                  class="w-full rounded-md shadow-sm form-input"
                  v-model="form.content"
                  rows="8"
                ></textarea>
                <button
                  class="px-4 py-2 font-bold text-white bg-blue-500 rounded-md hover:bg-blue-700"
                >
                  Crear
                </button>
              </form>
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
  data() {
    return {
      form: {
        excerpt: "",
        content: "",
      },
    };
  },
  methods: {
    submit() {
      this.$inertia.post(this.route("notes.store"), this.form);
    },
  },
};
</script>
