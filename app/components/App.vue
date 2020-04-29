<template>
    <Page>
        <ActionBar title="My NativeScript App" />
        <StackLayout>
            <BottomNavigation height="100%">
                <TabStrip>
                    <TabStripItem>
                        <Label text="Home"></Label>
                        <Image src="res://home"></Image>
                    </TabStripItem>
                    <TabStripItem>
                        <Label text="Settings"></Label>
                        <Image src="res://settings"></Image>
                    </TabStripItem>
                    <TabStripItem>
                        <Label text="Search"></Label>
                        <Image src="res://search"></Image>
                    </TabStripItem>
                </TabStrip>
                <TabContentItem>
                    <GridLayout>
                        <Home />
                    </GridLayout>
                </TabContentItem>
                <TabContentItem>
                    <GridLayout>
                        <Settings />
                    </GridLayout>
                </TabContentItem>
                <TabContentItem>
                    <GridLayout>
                        <Search/>
                    </GridLayout>
                </TabContentItem>
            </BottomNavigation>
        </StackLayout>
    </Page>
</template>

<script>
    import Home from "./pages/Home";
    import Settings from "./pages/Settings";
    import Search from "./pages/Search";
    export default {
        data() {
            return {};
        },
        components: {
            Home,
            Settings,
            Search
        }
    };
</script>

<style scoped>

</style>