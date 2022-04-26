<template>
    <div class="container-fluid">
        <div class="col-md-5">
            <textarea v-model="content1" id="editor1"></textarea>
        </div>
        <div class="col-md-1">
            <div class="action-group">
                <div class="action-group-name">Copy</div>
                <div class="action-buttons">
                    <button title="Copy the contents of the right panel to the left panel">
                        <svg aria-hidden="true" focusable="false" data-prefix="fas" data-icon="chevron-left" class="svg-inline--fa fa-chevron-left " role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512">
                        <path fill="currentColor" d="M224 480c-8.188 0-16.38-3.125-22.62-9.375l-192-192c-12.5-12.5-12.5-32.75 0-45.25l192-192c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25L77.25 256l169.4 169.4c12.5 12.5 12.5 32.75 0 45.25C240.4 476.9 232.2 480 224 480z"></path>
                        </svg>
                    </button>
                    <button title="Copy the contents of the left panel to the right panel">
                        <svg aria-hidden="true" focusable="false" data-prefix="fas" data-icon="chevron-right" class="svg-inline--fa fa-chevron-right " role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512">
                        <path fill="currentColor" d="M96 480c-8.188 0-16.38-3.125-22.62-9.375c-12.5-12.5-12.5-32.75 0-45.25L242.8 256L73.38 86.63c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0l192 192c12.5 12.5 12.5 32.75 0 45.25l-192 192C112.4 476.9 104.2 480 96 480z"></path>
                        </svg>
                    </button>
            </div>
            </div>
        </div>
        <div class="col-md-5">
            <textarea v-model="content2" id="editor2"></textarea>
        </div>
    </div>
</template
>


<script>
    
import CodeMirror from '../../../codemirror/codemirror-5.65.3'
import '../../../codemirror/codemirror-5.65.3/lib/codemirror.js'
import '../../../codemirror/codemirror-5.65.3/lib/codemirror.css'
import '../../../codemirror/codemirror-5.65.3/theme/ayu-dark.css'
import '../../../codemirror/codemirror-5.65.3/addon/lint/lint.css'
import '../../../codemirror/codemirror-5.65.3/mode/javascript/javascript.js'
import '../../../codemirror/codemirror-5.65.3/mode/css/css.js'
import '../../../codemirror/codemirror-5.65.3/addon/lint/json-lint.js'
import '../../../codemirror/codemirror-5.65.3/addon/lint/lint.js'

export default {
    name: "TextEditor",
    data(){
        return {
content1: `[
    {
        _id: "post 1",
        "author": "Bob",
        "content": "..."
        "page_views": 5
    },
    {
        "_id": "post 2",
        "author": "Bob",
        "content": "...",
        "page_views": 9
    },
    {
        "_id": "post 3",
        "author": "Bob",
        "content": "...",
        "page_views": 8
    }
]
`,
content2: `[
    {
        "array": [
            1
            2,
            3
        ],
        "boolean": true,
        "color": "gold"
        "null": null,
        "number": 123,
        "object": {
            "a": "b",
            "c": "d"
        },
        "string": "Hello Dave"
    },
    {
        "abcd": "dsvasdf"
    }
]
`
        }
    },
    mounted(){
        CodeMirror.fromTextArea(document.getElementById('editor1'),{
            lineNumbers: true,
            theme: 'ayu-dark',
            mode: "application/json",
            gutters: ["CodeMirror-lint-markers"],
            lint: true
        })
        CodeMirror.fromTextArea(document.getElementById('editor2'),{
            lineNumbers: true,
            mode: "application/json",
            gutters: ["CodeMirror-lint-markers"],
            lint: true,
            theme: 'ayu-dark'
        })
    }
}

</script>

<style scoped>

.container-fluid{
    margin-top: 100px;
}
.action-group {
    border-radius: 3px;
    display: flex;
    flex-direction: column;
}
.action-buttons {
    display: flex;
    gap: 5px;
}
.action-group .action-group-name {
    padding: 0 0 5px;
    text-align: center;
}
.action-buttons button {
    background: #dadada;
    border: none;
    border-radius: 3px;
    color: #4d4d4d;
    cursor: pointer;
    flex: 1 1;
    font-family: -apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Oxygen,Ubuntu,Cantarell,Fira Sans,Droid Sans,Helvetica Neue;
    font-size: 11pt;
    padding: 10px 15px;
}
</style>
