<template>
    <table v-if="messages.length">
      <thead>
        <tr>
          <th>Imię</th>
          <th>Nazwisko</th>
          <th>E-mail</th>
          <th>Wiadomość</th>
          <th>Data</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(message, index) in messages" :key="index">
          <td>{{ message.firstName }}</td>
          <td>{{ message.lastName }}</td>
          <td>{{ message.email }}</td>
          <td>{{ message.message }}</td>
          <td>{{ message.createdAt }}</td>
        </tr>
      </tbody>
    </table>
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
  
  <style>
  /* Opcjonalne style */
  table {
    width: 100%;
    border-collapse: collapse;
  }
  
  table th,
  table td {
    border: 1px solid #ccc;
    padding: 8px;
  }
  </style>
  