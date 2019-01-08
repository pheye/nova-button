<template>
    <div class="flex w-full justify-end items-center">
        <component 
            v-for="button in buttons"
            :is="button.component"
            :key="button.id"
            :field="button"
        />
    </div>
</template>

<script>
export default {
    props: ['resource', 'resourceName', 'resourceId'],

    computed: {
        buttons()
        {
            var buttons = [];

            var fields = _.toArray(JSON.parse(JSON.stringify(this.resource.fields)))

            fields.forEach(field => {
                if (field.component === 'nova-button' && field.showInToolbar) {
                    buttons.push(field);
                }
            })

            return _.toArray(buttons);
        }
    }
}
</script>