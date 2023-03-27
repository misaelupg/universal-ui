<script lang="ts">
    export let placeholder = "";
    export let id = "";
    export let name = "";
    export let label = "";
    export let type = "text";

</script>

<label class="opacity-50 pl focus:border-none font-medium mb-1 text-xs block" for={id}>{label}</label>
<input on:focus on:blur {type} id={id} {name} class="focus:outline outline-2 w-full outline-gray-300 border-gray-300 border rounded-lg py-2 px-3" {placeholder} />
