<template>
  <div class="overflow-x-auto">
    <table v-if="messages.length" class="min-w-full bg-white">
      <thead class="bg-gray-800 text-white">
        <tr>
          <th class="w-1/6 py-3 px-4 uppercase font-semibold text-sm">Imię</th>
          <th class="w-1/6 py-3 px-4 uppercase font-semibold text-sm">Nazwisko</th>
          <th class="w-1/6 py-3 px-4 uppercase font-semibold text-sm">E-mail</th>
          <th class="w-1/3 py-3 px-4 uppercase font-semibold text-sm">Wiadomość</th>
          <th class="w-1/6 py-3 px-4 uppercase font-semibold text-sm">Data</th>
        </tr>
      </thead>
      <tbody class="text-gray-700">
        <tr v-for="(message, index) in messages" :key="index">
          <td class="w-1/6 py-3 px-4">{{ message.firstName }}</td>
          <td class="w-1/6 py-3 px-4">{{ message.lastName }}</td>
          <td class="w-1/6 py-3 px-4">{{ message.email }}</td>
          <td class="w-1/3 py-3 px-4">{{ message.message }}</td>
          <td class="w-1/6 py-3 px-4">{{ message.createdAt }}</td>
        </tr>
      </tbody>
    </table>
    <p v-else class="text-center text-gray-500">Brak wiadomości do wyświetlenia.</p>
  </div>
</template>

<script>
export default {
  name: 'MessageTable',
  props: {
    messages: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
</style>
