<template>
    <div class="flex border-b border-40 nova-button-wrapper">
        <div class="w-1/4 py-4">
            <label class="font-normal text-80">{{ field.label }}</label>
        </div>
        <div class="w-3/4 py-4">
            <nova-button v-bind="$props" />
        </div>
    </div>
</template>

<script>
export default {
    props: ['resource', 'resourceName', 'resourceId', 'field']
}
</script>