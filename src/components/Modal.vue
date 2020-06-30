<template>
    <div class="w-full h-screen items-center justify-center flex">
        <button class="bg-red-600 px-3 py-1 text-white hover:bg-red-800" @click="active = true">Open Modal</button>
        <div class="bg-gray-500 opacity-75 w-full h-full fixed top-0 left-0 " @click="active = false"
             v-if="active"></div>
        <div class="shadow absolute z-10 bg-white w-1/2" v-if="active">
            <button
                    class="absolute right-0 top-0 -mx-2 -mt-2 flex items-center justify-center w-8 h-8 rounded-full bg-gray-600 text-white hover:bg-gray-800"
                    @click="active = false">
                x
            </button>
            <div>
                <slot></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Modal',
    data() {
        return {
            active: true
        }
    },
}
</script>