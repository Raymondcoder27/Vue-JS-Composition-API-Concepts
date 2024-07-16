<template>
    <div class="modals">
        <h1>Modals</h1>
        <div>
            <label for="">
                Show dark modals?
                <input
                v-model="showDarkModals"
                 type="checkbox">
            </label>
        </div>
        <pre>{{ showDarkModals }}</pre>
        <button @click="showModal = true">Show Modal</button>
        <component 
        v-model="showModal"
        :is="showDarkModals ? ModalDark : Modal"
        title="My modal title via prop"
        >
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorum corporis sed ab.</p>
    </component>
    </div>
</template>

<script setup>
    //imports
    import {ref} from 'vue'
    import Modal from '@/components/Modal.vue';
    import ModalDark from '@/components/ModalDark.vue'

    const showDarkModals = ref(false)
    const showModal = ref(false)

    // const props = defineProps({ userData: {
    //     type: Object
    // }})
</script>

