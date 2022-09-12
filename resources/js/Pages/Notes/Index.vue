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
              <h3 class="text-lg text-gray-900">Listado de notas</h3>
              <p class="text-sm text-gray-600">
                Toma el registro correcto y ejecuta cualquier función (ver,
                editar o eliminar)
              </p>
            </div>
          </div>
          <div class="mt-5 md:col-span-2 md:mt-0">
            <div class="p-4 bg-white shadow md:rounded-md">
              <div class="flex justify-between">
                <input
                  type="text"
                  class="rounded-md shadow-sm form-input"
                  placeholder="Buscar..."
                  v-model="q"
                />

                <inertia-link
                  :href="route('notes.create')"
                  class="px-4 py-2 font-bold text-white bg-blue-500 rounded-md"
                >
                  Crear
                </inertia-link>
              </div>
              <hr class="my-6" />
              <table>
                <tr v-for="note in notes" :key="note.id">
                  <td class="px-4 py-2 border">
                    {{ note.excerpt }}
                  </td>
                  <td class="px-4 py-2">
                    <inertia-link :href="route('notes.show', note.id)">
                      Ver
                    </inertia-link>
                  </td>
                  <td class="px-4 py-2">
                    <inertia-link :href="route('notes.edit', note.id)">
                      Editar
                    </inertia-link>
                  </td>
                </tr>
              </table>
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
    notes: Array,
  },
  data: function () {
    return {
      q: "",
    };
  },
  watch: {
    q: function (value) {
      this.$inertia.replace(this.route("notes.index", { q: value }));
    },
  },
};
</script>
