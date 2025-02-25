<script>
export default {
    props: {
        modelValue: { type: String, default: "" }, //prop nhận dữ liệu từ component cha (dùng để binding giá trị ô nhập liệu).
    },
    emits: ["submit", "update:modelValue"], //sự kiện submit và sự kiện update
    methods: {
        updateModelValue(e) {
            this.$emit("update:modelValue", e.target.value);
        },
        submit() {
            this.$emit("submit");
        },
    },
};
</script>
<template>
    <div class="input-group">
        <input type="text" class="form-control" placeholder="Nhập thông tin cần tìm" :value="modelValue"
            @input="updateModelValue" @keyup.enter="submit" />
        <div class="input-group-append">
            <button class="btn btn-outline-secondary" type="button" @click="submit">
                <i class="fas fa-search"></i> Tìm kiếm
            </button>
        </div>
    </div>
</template>F