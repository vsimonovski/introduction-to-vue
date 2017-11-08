<template>
<div class="event">
    <strong>[{{data.startTime}} - {{data.endTime}}]</strong>
    <span>{{data.name}}</span>
    <span v-on:click="deleteEvent(data.id, roomName)" class="event__delete">x</span>
</div>
</template>

<script>
export default {
    name: 'Room',
    props: ['data', 'deleteEvent', 'roomName']
};
</script>

<style lang="scss">
.event {
    position: relative;
    &__delete {
        position: absolute;
        right: -15px;
        color: #c0392b;
        cursor: pointer;
    }
}
</style>
