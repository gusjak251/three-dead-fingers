<!-- Please remove this file from your project -->
<template>
    <div class="text-center w-48">
        <Title>{{ name }}</Title>
        <p class="text-gray-700 text-sm">{{ role }}</p>
        <img class="h-48 object-cover" :src="img" />
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
  