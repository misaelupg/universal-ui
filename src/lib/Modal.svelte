<script lang="ts">
    import {createEventDispatcher, onMount} from 'svelte';
    import Button from "./Button.svelte";
    import { fade } from 'svelte/transition';
    export let width = "500px";
    export let title = "";
    const dispatch = createEventDispatcher();

    onMount(() => {
        const dialog = getDialog();
        dialog.addEventListener('close', () => dialog.returnValue ? dispatch('close') : dispatch('confirm'))
    })

    function getDialog() {
        return document.getElementsByTagName("dialog")[0];
    }
    const closeDialog = (value) => {
        const dialog = getDialog();
        dialog.close(value);
    }

    export function show() {
        const dialog = getDialog();
        dialog.showModal();
    }

    export function close() {
        closeDialog(false);
    }

</script>

<dialog out:fade style="width: {width}" class="drop-shadow-2xl rounded-2xl p-0">
    <div class="w-full">
        <div class="pb-3 border-b-2 border-b-gray-100 p-4">
            <slot name="header">
                <p class="text-base opacity-100">{title}</p>
            </slot>
        </div>
        <div class="p-4">
            <slot name="body"></slot>
        </div>
        <div class="p-4 flex justify-end align-center space-x-2">
            <slot name="footer">
                <div>
                    <Button on:click={() => closeDialog(false)}>Cancelar</Button>
                </div>
                <div>
                    <Button on:click={() => closeDialog(true)} styleType="primary">Aceptar</Button>
                </div>
            </slot>
        </div>
    </div>
</dialog>

<style>

    dialog {
        transform: scale3d(0, 0, 1);
        transition: transform 200ms, opacity 150ms;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        position: fixed;
        inset-block-start: 0;
        inset-block-end: 0;
        max-width: calc((100% - 6px) - 2em);
        max-height: calc((100% - 6px) - 2em);
        user-select: text;
        visibility: visible;
        overflow: auto;
        opacity: 0;
    }

    dialog[open] {
        opacity: 1;
        transform: scale3d(1, 1, 1);
    }
    
</style>