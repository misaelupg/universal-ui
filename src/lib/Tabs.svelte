<script lang="ts">

</script>

<div class="w-full tabs rounded-full bg-gray-100 p-1">
    <div class="flex justify-between align-middle">
        <slot name="tabs"></slot>
    </div>
</div>
<div class="w-full">
    <slot name="tabs-content"></slot>
</div>
