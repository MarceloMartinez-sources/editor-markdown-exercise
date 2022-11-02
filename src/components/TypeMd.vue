<template>
    <textarea class="editor" v-model="editor"></textarea>
    <div class="preview" v-html="preview"></div>
</template>


<script setup>
    import { ref,  computed } from "vue";
    import { marked } from "marked";

    import hljs from "highlight.js"
    import "highlight.js/styles/rainbow.css"



    const editor = ref("");



    const preview = computed(()=>{

        marked.setOptions({
            renderer: new marked.Renderer(),
            highlight: function(code, lang) {
                const language = hljs.getLanguage(lang) ? lang : 'plaintext';
                return hljs.highlight(code, { language }).value;
            },
            langPrefix: 'hljs language-',
            pedantic: false,
            gfm: true,
            breaks: false,
            sanitize: false,
            smartypants: false,
            xhtml: false
            });

        return marked.parse(editor.value);
    });

</script>


<style>
    #app{
        height: 100vh;
        display:flex;
    }

    .editor, 
    .preview{
        padding: 10px;
    }

    .editor{
        border: solid 1px #f1f1f1;
        font-size: 18px;
        flex-grow: 1;
        outline: none;
    }

    .preview{
        background: #f1f1f1;
        overflow-y: scroll;
        width: 40%;

    }
</style>