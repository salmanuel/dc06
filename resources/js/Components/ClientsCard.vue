<template>
    <div class="table">
      <table class="table-fixed border">
        <!-- <thead>
          <tr>
            <th class="bg-gray-200 px-4 py-2">Last Name</th>
            <th class="bg-gray-200 px-4 py-2">First Name</th>
            <th class="bg-gray-200 px-4 py-2">Address</th>
            <th class="bg-gray-200 px-4 py-2">Level</th>
          </tr>
        </thead> -->
        <tbody>
          <tr>
            <td class="border px-4 py-2">{{ client.last_name }}</td>
            <td class="border px-4 py-2">{{ client.first_name }}</td>
            <td class="border px-4 py-2">{{ client.address }}</td>
            <td class="border px-4 py-2">{{ client.level }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script setup>
  const props = defineProps({
    client: Object
  });
  </script>
  