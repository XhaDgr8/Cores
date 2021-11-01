<template>
    <div>
        <welcome/>
    </div>
</template>

<script>
    import { defineComponent } from 'vue'
    // import AppLayout from '@/Layouts/AppLayout.vue'
    import Welcome from '@/Jetstream/Welcome.vue'

    export default defineComponent({
        components: {
            // AppLayout,
            Welcome,
        },
    })
</script>
