<template>
    <teleport to=".modals-container">
            <div
            v-if="modelValue"
         class="modal">
            <h1>{{ title }}</h1> 
            <!-- <h1>This is a modal</h1> -->
            <slot />
            <button @click="$emit('update:modelValue', false)">Hide Modal</button>
            <!-- <pre>{{ $slots.title }}</pre> -->
            <!-- <button @click="showModal = false">Hide modal</button> -->
            <div>
                Username is: {{ userData.username }}
            </div>
        </div>
        </teleport>
</template>

<script setup>
    // import { useSlots } from 'vue';

    // const slots = useSlots()

    // console.log(slots.title())
    import {inject} from 'vue'

    const userData = inject('userData')

    const props = defineProps({
        modelValue: {
            type: Boolean,
            default: false
        },
        title: {
            type: String,
            default: 'No title specified.'
        }
    })


    // console.log(props.title)

    const emit = defineEmits(['update:modelValue'])

    // const handleButtonClick = () => {
    //     emit('update:modelValue', false)
    // }
</script>

<style scoped>
    .modal{
        background: beige;
        padding: 10px;
        position: absolute;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        z-index: 1;
    }
</style>