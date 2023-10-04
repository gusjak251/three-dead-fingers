<!-- Please remove this file from your project -->
<template>
    <div>
        <div class="flex flex-row w-1/3 mx-auto">
            <button>
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="gray"
                    class="w-6 h-6">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 12h-15m0 0l6.75 6.75M4.5 12l6.75-6.75" />
                </svg>
            </button>
            <div v-for="image in images" :key="image.link" class="p-4">
                <img :src="image.link" class="h-36 w-48 cursor-pointer hover:opacity-75" @click="selectImage(image)" />
            </div>
            <button>
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="gray"
                    class="w-6 h-6">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M4.5 12h15m0 0l-6.75-6.75M19.5 12l-6.75 6.75" />
                </svg>
            </button>
        </div>
        <div v-if="showModal"
            class="fixed flex justify-center items-center w-screen h-screen bg-black bg-opacity-50 left-0 top-0 z-50">
            <p class="text-center fixed top-10 mx-auto text-white text-lg">{{ selectedImage.text }}</p>
            <img v-click-outside="closeModal" :src="selectedImage.link" class="sm:w-3/4 md:w-1/2 text-center mx-auto" />
        </div>
    </div>
</template>
  
<script>
import vClickOutside from 'v-click-outside'
export default {
    name: 'Press-Photos',
    directives: {
        clickOutside: vClickOutside.directive
    },
    methods: {
        selectImage(image) {
            this.selectedImage = image;
            this.showModal = true;
        },
        closeModal() {
            this.showModal = false;
        }
    },
    data() {
        return {
            images: [
                {
                    'link': 'images/fiskis.jpg',
                    'text': 'Fiskis playing guitar'
                },
                {
                    'link': 'images/logo.png',
                    'text': 'Fiskis playing guitar'
                }
            ],
            selectedImage: {
                'link': '',
                'text': 'Image not found'
            },
            showModal: false,
        }
    }
}
</script>
  