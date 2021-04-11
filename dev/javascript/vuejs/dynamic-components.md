# Dynamic Components

Man kann Components dynamisch einbinden. Hilfreich für Tabs oder Widgets.

```vue
<template>
    <div
        <component v-bind:is="componentName"></component>
    </div>
</template>

<script>
    import MyDynamicComponent from './components/MyDynamicComponent';

    export default {

        components: {
            MyDynamicComponent,
        },

        data () {
            return {
                componentName: 'MyDynamicComponent'
            };
        },

    };
</script>
```

- [Dynamic Components](https://vuejs.org/v2/guide/components.html#Dynamic-Components)