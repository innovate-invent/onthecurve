<template>
    <v-card>
        <v-file-input
            @change="load"
            dense
            hide-details="auto"
            label="CSV Data"
            placeholder="Upload grades"
            show-size
            solo
        />
    </v-card>
</template>

<script lang="ts">
    import { Component, Prop, Watch, Vue } from 'vue-property-decorator';
    import XLSX from 'xlsx';

    @Component({ components: {} })
    export default class ImportData extends Vue {
        $refs!: {};

        async load(file: File): Promise<void> {
            const workbook = XLSX.read(await file.arrayBuffer(), { type: 'array' });
            // TODO transform workbook into useable data
        }
    }
</script>

<style scoped></style>
