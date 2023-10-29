<!-- Please remove this file from your project -->
<template>
    <div>
        <div class="flex flex-row justify-center mx-auto md:w-3/4 sm:w-3/4">
            <button @click="scroll(-1)">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="gray"
                    class="w-6 h-6">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 12h-15m0 0l6.75 6.75M4.5 12l6.75-6.75" />
                </svg>
            </button>
            <div v-for="image in filterImages()" :key="image.link" class="p-4">
                <img :src="image.link" class="h-48 object-cover cursor-pointer hover:opacity-75 transition-all"
                    @click="selectImage(image)" />
            </div>
            <button @click="scroll(1)">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="gray"
                    class="w-6 h-6">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M4.5 12h15m0 0l-6.75-6.75M19.5 12l-6.75 6.75" />
                </svg>
            </button>
        </div>
        <div class="flex flex-row justify-center gap-x-2 p-2">
            <div v-for="(image, index) in images" :key="index" @click="
                position = index;
            " class="cursor-pointer">
                <div class="h-2 w-2 rounded-full bg-gray-200" v-if="index == position" />
                <div v-else class="h-2 w-2 rounded-full bg-gray-500" />
            </div>
        </div>
        <div v-if="showModal"
            class="fixed flex justify-center items-center w-screen h-screen bg-black bg-opacity-50 left-0 top-0 z-50">
            <p class="text-center fixed top-10 mx-auto text-white text-lg">{{ selectedImage.text }}</p>
            <img v-click-outside="closeModal" :src="selectedImage.link" class="sm:h-1/2 md:h-3/4 text-center mx-auto" />
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
        scroll(direction) {
            if (this.images.length <= this.imageCount) {
                return;
            }
            const step = this.position + direction;
            if (step > this.images.length - 1) {
                this.position = 0;
            } else if (step < 0) {
                this.position = this.images.length - 1;
            } else {
                this.position = step;
            }

            console.log(this.position);
        },
        filterImages() {
            if (this.images.length <= this.imageCount) {
                return this.images;
            }
            if (this.position + this.imageCount - 1 > this.images.length - 1) {
                let merged_images = this.images.slice(this.position, this.images.length);
                const diff = this.imageCount - merged_images.length;
                this.images.slice(0, diff).forEach(image => {
                    merged_images.push(image);
                });
                console.log(merged_images);
                return merged_images;
            }
            return this.images.slice(this.position, this.position + this.imageCount);
        },
        closeModal() {
            this.showModal = false;
        }
    },
    data() {
        return {
            images: [
                {
                    'link': 'images/sweden-rock.jpg',
                    'text': 'Sweden rock festival 2018'
                },
                {
                    'link': 'images/fiskis.jpg',
                    'text': 'Fiskis playing guitar'
                },
                {
                    'link': 'images/henry.JPG',
                    'text': 'Henry behind the drums'
                },
                {
                    'link': 'images/band-photo.JPG',
                    'text': 'Band photo'
                },
                {
                    'link': 'images/oliwer.JPG',
                    'text': 'Oliwer on stage'
                },
                {
                    'link': 'images/header-image.JPG',
                    'text': 'Band photo'
                },
            ],
            selectedImage: {
                'link': '',
                'text': 'Image not found'
            },
            showModal: false,
            position: 0,
            imageCount: 3,
        }
    }
}
</script>
  