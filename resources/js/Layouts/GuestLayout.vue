<script setup>
import { Head, Link } from '@inertiajs/inertia-vue3'
import ApplicationMark from '@/Components/ApplicationMark.vue'
import Banner from '@/Components/Banner.vue'

defineProps({
  title: String,
})
</script>

<template>
  <div>

    <Head :title="title" />

    <Banner />

    <div class="min-h-screen bg-gray-100">
      <nav class="bg-white border-b border-gray-100">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="flex justify-between h-16">
            <div class="flex">
              <div class="shrink-0 flex items-center">
                <Link :href="route('dashboard')">
                <ApplicationMark class="block h-9 w-auto" />
                </Link>
              </div>
            </div>
          </div>
        </div>
      </nav>

      <header v-if="$slots.header" class="bg-white shadow">
        <div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
          <slot name="header" />
        </div>
      </header>

      <main>
        <slot />
      </main>
    </div>
  </div>
</template>
