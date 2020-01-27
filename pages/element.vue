<template>
    <div style="padding: 30px;">
        <div>
            <el-button v-on:click="visible = true">Open Dialog</el-button>
        </div>
        <div>
            <el-dialog :visible.sync="visible" title="Hello world">
                <p>Try Element</p>
            </el-dialog>
        </div>
        <div class="block">
            <span class="demonstration">With default time</span>
            <el-date-picker
                v-model="datetime1"
                type="datetime"
                placeholder="出勤時刻を入力してね"
                default-time="12:00:00">
            </el-date-picker>
        </div>
        <div>
            <el-time-picker
                v-model="time1"
                :picker-options="{
                    selectableRange: '00:00:00 - 23:59:59'
                }"
                placeholder="Arbitrary time">
            </el-time-picker>
            <el-time-picker
                v-model="time2"
                :picker-options="{
                    selectableRange: '00:00:00 - 23:59:59'
                }"
                placeholder="Arbitrary time">
            </el-time-picker>
        </div>
    </div>
</template>

<script>
export default {
    data : function () {
        return {
            visible: false,
            time1: '',
            time2: '',
            datetime1: ''
}
    }
}
</script>