<script setup>
defineProps({
    alert_msg: {
        type: String,
        default: null
    },
    warning_msg: {
        type: String,
        default: null
    },
    line_alert_msg: {
        type: String,
        default: null
    },
    line_warning_msg: {
        type: String,
        default: null
    }
});

</script>

<template>
    <link href="https://getbootstrap.com/docs/5.3/assets/css/docs.css" rel="stylesheet">
    <div v-if="alert_msg || warning_msg"  class="p-3 bg-body rounded shadow-sm">
        <div v-if="alert_msg" class="alert alert-primary d-flex align-items-center">
            <svg xmlns="http://www.w3.org/2000/svg" class="bi bi-exclamation-triangle-fill flex-shrink-0 me-2" viewBox="0 0 16 16">
                <path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0M8 4a.905.905 0 0 0-.9.995l.35 3.507a.552.552 0 0 0 1.1 0l.35-3.507A.905.905 0 0 0 8 4m.002 6a1 1 0 1 0 0 2 1 1 0 0 0 0-2"/>
            </svg>
            <div>{{ alert_msg }}</div>
        </div>

        <div v-else-if="warning_msg">
            <div class="alert alert-danger d-flex align-items-center">
                <svg xmlns="http://www.w3.org/2000/svg" class="bi bi-exclamation-triangle-fill flex-shrink-0 me-2" viewBox="0 0 16 16">
                    <path d="M8.982 1.566a1.13 1.13 0 0 0-1.96 0L.165 13.233c-.457.778.091 1.767.98 1.767h13.713c.889 0 1.438-.99.98-1.767zM8 5c.535 0 .954.462.9.995l-.35 3.507a.552.552 0 0 1-1.1 0L7.1 5.995A.905.905 0 0 1 8 5m.002 6a1 1 0 1 1 0 2 1 1 0 0 1 0-2"/>
                </svg>
                <div>錯誤訊息</div>
            </div>
            <div class="d-flex justify-content-md-center">
                <div class="d-block text-danger fs-4">{{ warning_msg }}</div>
            </div>
        </div>

        <small class="d-block text-end mt-3">
            <button type="button" class="btn btn-secondary" @click="$router.back()">回上一頁</button>
        </small>
    </div>

    <div v-if="line_alert_msg" class="bg-body rounded shadow-sm">
        <div class="mb-2 oaerror primary">
            <h5><strong>{{ line_alert_msg }}</strong></h5>
        </div>
    </div>

    <div v-if="line_warning_msg" class="bg-body rounded shadow-sm">
        <div class="mb-2 oaerror danger">
            <h5><strong>Error - </strong>{{ line_warning_msg }}</h5>
        </div>
    </div>
</template>

<style scoped>
@import "@/assets/css/alert_message.css";
</style>