<template>
    <div class="text-white">
        <h3 class="text-xl font-bold">{{ author }}</h3>
        <p>{{ rating }}</p>
        <p class="italic">{{ quote }}</p>
        <a :href="url" target="_blank" class="hover:opacity-70">Read the review</a>
    </div>
</template>
  
<script>
export default {
    name: 'Review',
    props: {
        author: String,
        rating: String,
        quote: String,
        url: String
    }
}
</script>
  