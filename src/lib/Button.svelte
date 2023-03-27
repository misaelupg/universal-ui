<script lang="ts">
    export let styleType = "default";

    const COMMON_STYLES_CLASS = "w-full tracking-wide py-2 px-6 rounded-full focus:outline outline-offset-2 outline-2 outline-gray-300"
    const CLASSES = {
        default: "hover:bg-gray-100 active:bg-gray-200 " + COMMON_STYLES_CLASS,
        primary: "bg-black text-white hover:bg-gray-700 active:bg-teal-700 shadow-sm" + COMMON_STYLES_CLASS,
    }

</script>
<button on:click {...$$restProps} class={CLASSES[styleType]}>
    <slot></slot>
</button>