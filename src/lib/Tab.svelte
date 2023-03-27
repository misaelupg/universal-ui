
<script lang="ts">
    import type {TabValue} from "../types/TabValue.type";

    export let value: TabValue = 0;
    export let activeTab = false;
    const COMMON_STYLES = "rounded-full grow basis-0 rounded-full py-1 focus:outline outline-2  outline-offset-2 outline-gray-300";
    const ACTIVE_STYLE = "bg-white shadow " + COMMON_STYLES;
    const DEFAULT_STYLE= "" + COMMON_STYLES

</script>
<button data-value={value} on:click class={value === activeTab ? ACTIVE_STYLE : DEFAULT_STYLE}><slot></slot></button>
<style>
</style>