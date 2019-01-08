<template>
    <div class="flex w-full justify-end items-center">
        <component 
            v-for="button in buttons"
            :key="button.id"
            :is="button.component"
            :resourceName="resourceName"
            :resourceId="resourceId"
            :resource="resource"
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