<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head, Link } from '@inertiajs/vue3';

defineProps({
    reports: {
        type: Array,
    },
});

</script>

<template>
    <Head title="自分レポート一覧" />

    <AuthenticatedLayout>
        <template #header>
            <div class="flex items-center justify-between">
                <h2 class="font-semibold text-xl text-gray-800 leading-tight">自分レポート一覧</h2>
                <Link :href="route('report.create')"><button class="px-3 py-1 bg-blue-500 text-white rounded hover:bg-blue-600">レポート作成</button></Link>
            </div>
        </template>
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
            <div v-for="report in reports" :key="report.id">
                <div class="bg-white border rounded-lg overflow-hidden shadow-md mt-5">
                    <div class="w-full h-32 bg-blue-200" />
                    <div class="p-4">
                        <h2 class="text-xl font-semibold">{{ report.title }}</h2>
                        <p class="text-gray-600">{{ report.content }}</p>
                        <a @click="handleReportClick(report)" class="text-blue-500 hover:underline cursor-pointer">詳細を見る</a>
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>

<script>
export default
    {
        methods: {
            handleReportClick(report) {
                console.log(`クリックされたレポート: ${report.title}`);
            },
        },
    };
</script>