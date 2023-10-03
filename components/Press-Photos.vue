<!-- Please remove this file from your project -->
<template>
    <div class="flex flex-row w-1/3 mx-auto">
        <button>
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="gray"
                class="w-6 h-6">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 12h-15m0 0l6.75 6.75M4.5 12l6.75-6.75" />
            </svg>
        </button>
        <div v-for="image in images" :key="image.link" class="p-4">
            <img :src="image.link" class="h-36 w-48" />
        </div>
        <button>
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="gray"
                class="w-6 h-6">
                <path stroke-linecap="round" stroke-linejoin="round" d="M4.5 12h15m0 0l-6.75-6.75M19.5 12l-6.75 6.75" />
            </svg>
        </button>
    </div>
</template>
  
<script>
export default {
    name: 'Press-Photos',
    data() {
        return {
            images: [
                {
                    'link': 'images/fiskis.jpg',
                    'text': 'Fiskis playing guitar'
                },
                {
                    'link': 'images/8aE1K5YA.png',
                    'text': 'Fiskis playing guitar'
                }
            ]
        }
    }
}
</script>
  