<script>
export default {
    name: "ConcertCard",
    props: {
        name: String,
        location: String,
        date: String,
        description: String,
        link: String
    },
    emits: ["copy"],
    methods: {
        copyEmail(email) {
            navigator.clipboard.writeText(email);
            this.$emit("copy");
        }
    }
}
</script>

<template>
    <div class="flex flex-col card rounded-md px-3.5 py-2">
        <div class="mb-2.5 flex flex-col">
            <div class="flex flex-row justify-between items-center">
                <span class="text-white font-medium text-lg">{{ name }}</span>
                <time class="text-white">{{ date }}</time>
            </div>
            <span class="text-gray-500 text-base">{{ location }}</span>
        </div>
        <span class="w-full h-px bg-gray-500 mb-2.5"></span>
        <p class="text-white">{{ description }}</p>
        <a :href="link" class="text-gray-300 underline" rel="noopener" target="_blank">Go to event</a>
    </div>
</template>

<style scoped>
.card {
    background-color: #2a2a2a;
}
</style>