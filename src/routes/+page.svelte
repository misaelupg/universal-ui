<script lang="ts">

    import Modal from "$lib/Modal.svelte";
    import TextArea from "$lib/TextArea.svelte";
    import Tabs from "$lib/Tabs.svelte";
    import Tab from "$lib/Tab.svelte";
    import {onMount} from "svelte";
    import TabContent from "$lib/TabContent.svelte";
    import TabContentItem from "$lib/TabContentItem.svelte";
    import TextField from "$lib/TextField.svelte";
    import ComboBox from "$lib/ComboBox.svelte";

    let activeTab = "setActive";
    let modal;

    onMount(() => {
        modal.show();
    })

    function onTabClick(value) {
        activeTab = value;
    }
</script>

<button on:click={() => modal.show()}>Open</button>

<Modal bind:this={modal} title="Create a new assignment" width="400px" on:close={() => modal.hide()}>
    <div slot="body">
        <div class="mb-4">
            <Tabs>
                <svelte:fragment slot="tabs">
                    <Tab on:click={() => onTabClick("setActive")} value="setActive" {activeTab}>Set date</Tab>
                    <Tab on:click={() => onTabClick("relativeDate")} value="relativeDate" {activeTab}>Relative date</Tab>
                    <Tab on:click={() => onTabClick("anotherDate")} value="anotherDate" {activeTab}>Another date</Tab>
                </svelte:fragment>
                <svelte:fragment slot="tabs-content">
                    <TabContent>
                        <TabContentItem value="setActive" {activeTab}>
                            <p>This is some useful helper text that will help you fill the required information</p>
                            <div class="mt-3">
                                <TextField placeholder="example@example.com" label="Email" type="text"></TextField>
                            </div>
                            <div class="mt-3">
                                <TextField type="date" label="Fecha de entrega"></TextField>
                            </div>
                            <div class="mt-3">
                                <ComboBox label="Asignado a:"/>
                            </div>
                        </TabContentItem>
                        <TabContentItem value="relativeDate" {activeTab}>
                            <p>Relative text</p>
                        </TabContentItem>
                        <TabContentItem value="anotherDate" {activeTab}>
                            <p>Another text</p>
                            <p>
                                The native HTML element should be used in creating modal dialogs as it provides usability and
                                accessibility features that must be replicated if using other elements for a similar purpose. Use the
                                appropriate.
                            </p>
                            <div class="mt-4">
                                <TextArea label="Description" placeholder="Write down the description in here..."></TextArea>
                            </div>
                        </TabContentItem>
                    </TabContent>
                </svelte:fragment>
            </Tabs>
        </div>
    </div>
</Modal>
