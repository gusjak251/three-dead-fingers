<template>
    <div class="flex flex-col gap-4 md:gap-0 md:flex-row justify-evenly w-3/4 mx-auto">
        <div v-for="review in reviews" :key="review.url">
            <Review :author="review.author" :record="review.record" :rating="review.rating" :quote="review.quote"
                :url="review.url" />
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'Reviews',
    props: {
        light: {
            type: Boolean,
            default: false
        },
    },
    data() {
        return {
            reviews: [
                {
                    author: 'Metal Centre',
                    record: 'All Worlds Apart',
                    rating: '8.5/10',
                    quote: '"THREE DEAD FINGERS has great potential."',
                    url: 'https://www.metalcentre.com/2022/01/three-dead-fingers-all-worlds-apart/'
                },
                {
                    author: 'Deutsche metal',
                    record: 'All Worlds Apart',
                    rating: '9/10',
                    quote: '"Its the fookin best!"',
                    url: 'https://www.google.com'
                }
            ]
        }
    }
}
</script>
  