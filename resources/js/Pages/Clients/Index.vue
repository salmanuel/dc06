<template>
    <Head title="Clients"/>
    <Layout title="Clients">
       
            
      <div class="flex justify-between bg-gray-200">
        <h2 class="font-bold text-4xl text-gray-800 ml-8 mt-4 mb-4">Clients</h2>
      </div>

      <div class="mt-8">
          
          <div class="max-w-5xl mx-auto ">
              
              <!-- <ClientsCard v-for="client in props.clients" :client="client" :key="client.id"/> -->
              <table class="mt-4 table-auto w-full border-collapse">
                  <thead>
                    <tr>
                      <th class="px-4 py-2 bg-gray-200">Name</th>
                      <th class="px-4 py-2 bg-gray-200">Address</th>
                      <th class="px-4 py-2 bg-gray-200">Level</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr v-for="client in clients.data" :key="client.id">
                      <td class="border px-4 py-2">{{ client.last_name }}, {{ client.first_name }}</td>
                      <!-- <td class="border px-4 py-2">{{ client.first_name }}</td> -->
                      <td class="border px-4 py-2">{{ client.address }}</td>
                      <td class="border px-4 py-2">{{ client.level }}</td>
                    </tr>
                  </tbody>
                </table>
          </div>
      </div>
        <!-- <div class="mt-6">
            <template v-for="link in clients.links">
                <Link 
                    v-if="link.url"
                    :href="link.url" 
                    v-html="link.label" />
    
                    <span v-else v-html="link.label"></span>
                    
            </template>
        </div> -->
        <Pagination :links="clients.links" class="mt-6 flex justify-center"/>
    </Layout>
</template>

<script setup>
import Layout from '@/Layouts/Layout.vue'
import ClientsCard from '@/Components/ClientsCard.vue'
import Pagination from '@/Layouts/Pagination.vue'
import { Head, Link } from '@inertiajs/vue3';


const props = defineProps({
    clients: Object
})

</script>