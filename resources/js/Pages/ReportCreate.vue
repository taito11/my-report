<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';

defineProps({
});

</script>

<template>
    <Head title="自分レポート一覧" />

    <AuthenticatedLayout>
        <template #header>
            <div class="flex items-center justify-between">
                <h2 class="font-semibold text-xl text-gray-800 leading-tight">自分レポート作成</h2>
            </div>
        </template>
        <p>タイトルと内容を入力させる</p>
    </AuthenticatedLayout>
</template>

<script>
</script>