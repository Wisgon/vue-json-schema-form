# vue-json-schema-form
Quickly building HTML form based on `Vue`, `Json Schema` and `ElementUi`.

* [中文文档（推荐）](https://github.com/lljj-x/vue-json-schema-form/blob/master/README_zh-cn.md)

## Experience quickly
* [Live playground](https://form.lljj.me/ "Vue JSON Schema Form Demo")
* [Document](https://vue-json-schema-form.lljj.me/en/ "Vue JSON Schema Docs")
* [Github](https://github.com/lljj-x/vue-json-schema-form "Vue JSON Schema github")
* [Usage scenario - visual activity editor](https://form.lljj.me/vue-editor.html)
* [Todo](https://vue-json-schema-form.lljj.me/en/guide/todo.html)

![](https://7.luochongfei.top/vue-json-schema-form.gif?1)

``` bash
# npm
npm install --save @lljj/vue-json-schema-form

# yarn
yarn add @lljj/vue-json-schema-form
```

```vue
<template>
    <VueForm
        v-model="formData"
        :schema="schema"
    >
    </VueForm>
</template>

<script >
    import VueForm from '@lljj/vue-json-schema-form';

    export default {
        name: 'Demo',
        components: {
            VueForm
        },
        data() {
            return {
                formData: {},
                schema: {
                    type: 'object',
                    required: [
                        'firstName'
                    ],
                    properties: {
                        firstName: {
                            type: 'string',
                            title: 'First name',
                            default: 'Jun'
                        },
                        lastName: {
                            type: 'string',
                            title: 'Last name'
                        },
                    }
                }
            };
        }
    };
</script>
```

### Description
* Follow the JSON Schema specification, only need to give the `Json Schema`, you can generate the corresponding form
* Quickly configure personalized UI views and check error messages, which can be adapted to commonly used UI libraries. The default view of the current version depends on `ElementUi`.
* uses the [ajv validator](https://github.com/epoberezkin/ajv)
* Design ideas and reference to the schema analysis index [react-jsonschema-form](https://github.com/rjsf-team/react-jsonschema-form)

## Relevant
[JSON Schema](https://json-schema.org/understanding-json-schema/index.html) |
[Vue](https://cn.vuejs.org/) |
[Element Ui](https://element.eleme.io/)

### Why
Originated from shop decoration scenes, it can also be called front-end visual editing. In order to solve the universality of the component data configuration form, the form is generated through `Json Schema`.

The advantage of this is to solve the repetitive work of each configuration form, and the server can also maintain the same verification rules as the front-end based on the same schema.

## License
Apache-2.0
