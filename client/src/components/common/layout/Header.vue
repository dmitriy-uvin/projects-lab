<template>
    <VAppBar
        color="#DB2763"
        dense
        dark
        height="54"
    >
        <VTooltip bottom>
            <template v-slot:activator="{ on, attrs }">
                <VBtn icon dark
                      v-bind="attrs"
                      v-on="on"
                      @click="onHome"
                      class="mr-2"
                >
                    <VIcon>
                        mdi-home
                    </VIcon>
                </VBtn>
            </template>
            <span>My Home</span>
        </VTooltip>

        <VTooltip bottom>
            <template v-slot:activator="{ on, attrs }">
                <VBtn icon dark
                      v-bind="attrs"
                      v-on="on"
                      @click="onInbox">
                    <VIcon>
                        mdi-email
                    </VIcon>
                </VBtn>
            </template>
            <span>My inbox</span>
        </VTooltip>

        <VSpacer />

        <VToolbarTitle>
            <span class="app-name">ProjectsLab</span>
        </VToolbarTitle>

        <VSpacer />

        <CreateDropdown />

        <UserDropdown />
    </VAppBar>
</template>

<script>
import UserDropdown from "./UserDropdown";
import CreateDropdown from "@/components/common/layout/CreateDropdown";
import userMixin from "../../../mixins/userMixin";
export default {
    name: "Header",
    mixins: [userMixin],
    components: {
        UserDropdown,
        CreateDropdown
    },
    methods: {
        onSupport() {
            // this.$router.push({ name: 'support' });
        },
        onHome() {
            if (this.$route.name !== 'dashboard') this.$router.push({ name: 'dashboard' });
        },
        onInbox() {
            // this.$router.push({ name: 'inbox' });
        }
    }
}
</script>

<style scoped>
.app-name {
    font-weight: bold;
}
</style>