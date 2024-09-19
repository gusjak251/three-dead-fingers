<script>
export default {
    name: "ContactCard",
    props: {
        name: String,
        role: String,
        email: String
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
            <span class="text-white font-medium text-lg">{{ name }}</span>
            <span class="text-gray-500 text-base">{{ role }}</span>
        </div>
        <span class="w-full h-px bg-gray-500 mb-2.5"></span>
        <label class="text-gray-300 font-medium">Email address</label>
        <button class="text-white text-left" @click="copyEmail(email)">{{ email }}</button>
    </div>
</template>

<style scoped>
.card {
    background-color: #2a2a2a;
}
</style>