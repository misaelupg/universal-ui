<script lang="ts">
    let textarea;
    export let placeholder = "";
    export let id = "";
    export let name = "";
    export let label = "";

    function autosize(){
        setTimeout(function(){
            textarea.style.cssText = 'height:auto';
            textarea.style.cssText = 'height:' + textarea.scrollHeight + 'px';
        },0);
    }
</script>

<label class="opacity-50 focus:border-none font-medium mb-1 text-xs block" for={id}>{label}</label>
<textarea id={id} {name} class="focus:outline outline-2 outline-gray-300 border-gray-300 border rounded-lg py-2 px-3" bind:this={textarea} on:keydown={autosize} rows='1' {placeholder}></textarea>

<style>
    textarea{
        /* box-sizing: padding-box; */
        overflow:hidden;
        /* demo only: */
        color: rgba(0, 0, 0, .6);
        resize: none;
        width: 100%;
    }
</style>