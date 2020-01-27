<template>
    <div>
        <div>_id.vue</div>
        <p>{{ $route.params.id }}</p>
    </div>
</template>

<script>
export default {
    validate({ params }) {
        // true or false
        // if false display /layouts/error
        return /^\d+$/.test(params.id)
    }
}
</script>