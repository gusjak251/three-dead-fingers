<!-- Please remove this file from your project -->
<template>
    <div class="fixed bottom-10 w-fit mx-auto left-0 right-0 rounded-md px-3.5 py-2 bg-gray-900 transition-all ease" :class="{
        'scale-0 opacity-0': show == false,
        'scale-100 opacity-100': show
    }">
        <div class="flex flex-row gap-x-2 text-white">
            <p class="font-bold text-red-500">{{ title }}</p>
            <p class="mr-36">{{ text }}</p>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'Title',
    props: {
        show: Boolean,
        title: String,
        text: String,
    },
    watch: {
        show() {
            setTimeout(() => {
                this.$emit('hide');
            }, 3000);
        }
    }
}
</script>
  