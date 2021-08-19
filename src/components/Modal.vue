<template>
    <div class="backdrop" @click.self='this.$emit("closeModal")'>
        <div class="modal">
            <slot> </slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    //name: 'Modal',
    //props: ['header','text'],
    methods: {
        closeModal() {
            this.$emit("closeModal")
        }
    }
}
</script>


<style>
    .modal {
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }
    .backdrop {
        top: 0;
        position: fixed;
        background: rgba(0, 0, 0, 0.5);
        width: 100%;
        height: 100%;
        padding-top: 100px;
    }
    .modal h1 {
        color: green;
    }
    .modal .actions a{
        color:brown;
    }
</style>