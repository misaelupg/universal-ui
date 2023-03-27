<script lang="ts">
    export let activeTab = 0;
    export let value: string | number = 0;
    console.log(activeTab)
</script>
{#if value === activeTab}
    <div>
        <slot></slot>
    </div>
{/if}