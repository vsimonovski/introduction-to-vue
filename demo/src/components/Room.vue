<template>
<div class="room card">
    <h1 class="room__title">{{roomName}}</h1>
    <ul class="room__list">
        <li class="room__item" v-for="(event, index) in events" :key="index">
            <Event :data="event"  :roomName="roomName"
                :deleteEvent="deleteEvent"
            ></Event>
        </li>
    </ul>
</div>
</template>

<script>
import Event from '@/components/Event';

export default {
    name: 'Room',
    props: ['roomName', 'events', 'deleteEvent'],
    data() {
        return {};
    },
    components: {
        Event
    },
    methods: {}
};
</script>

<style lang="scss">
.room {
    &__list {
        list-style: none;
        padding-left: 0;
    }

    &__item {
        margin-bottom: 10px;
        font-size: 18px;
    }
}

.card {
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
    transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
    height: 400px;
    width: 300px;
    margin-right: 150px;
    background: #fff;
    border-top: 5px solid #e74c3c;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 2rem;

    &:hover {
        box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25),
            0 10px 10px rgba(0, 0, 0, 0.22);
    }

    &:last-child {
        margin-right: 0;
    }
}
</style>
