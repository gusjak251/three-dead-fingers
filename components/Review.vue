<template>
    <div class="text-white w-72">
        <h3 class="text-xl font-bold mb-2 text-center md:text-left">{{ author }}</h3>
        <p class="font-bold">{{ record }}</p>
        <p>{{ rating }}</p>
        <p class="italic">{{ quote }}</p>
        <a :href="url" target="_blank" class="hover:opacity-70 text-gray-500">Read the review</a>
    </div>
</template>
  
<script>
export default {
    name: 'Review',
    props: {
        author: String,
        record: String,
        rating: String,
        quote: String,
        url: String
    }
}
</script>
  