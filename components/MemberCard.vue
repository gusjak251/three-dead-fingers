<!-- Please remove this file from your project -->
<template>
    <div class="text-center md:w-48">
        <Title>{{ name }}</Title>
        <p class="text-gray-500 text-sm mb-2">{{ role }}</p>
        <img class="h-48 object-cover mx-auto mb-4 md:mb-0" :src="img" />
    </div>
</template>
  
<script>
export default {
    props: {
        name: String,
        role: String,
        img: String,
    },
    name: 'MemberCard'
}
</script>
  