<script lang="ts">
    import TextField from "./TextField.svelte";
    export let label = "";
    export let placeholder = "";
    let isOpen = false
</script>
<TextField on:focus={() => isOpen = true} on:blur={() => isOpen = false} type="text" {label} {placeholder}></TextField>

{#if isOpen}
    <div class="relative overflow-visible">
        <div class="shadow-2xl rounded-md py-2 fixed right-0 top-1 left-0 w-full bg-white z-10">
            <ul>
                <li>
                    <button class="py-2 px-4 focus:outline rounded-md text-left w-full outline-offset-2 outline-2 outline-gray-300 hover:bg-gray-100 active:bg-gray-200">
                        Misael Cázares
                    </button>
                </li>
                <li>
                    <button class="py-2 px-4 focus:outline rounded-md text-left w-full outline-offset-2 outline-2 outline-gray-300 hover:bg-gray-100 active:bg-gray-200">
                        Misael Cázares
                    </button>
                </li>
                <li>
                    <button class="py-2 px-4 focus:outline rounded-md text-left w-full outline-offset-2 outline-2 outline-gray-300 hover:bg-gray-100 active:bg-gray-200">
                        Misael Cázares
                    </button>
                </li>
            </ul>
        </div>
    </div>
{/if}
