<template>
  <div class="schedule">
     <Room :roomName="'Milutin Milankovic'" :events="events.MilutinMilankovic"
     :deleteEvent="deleteEvent"
     ></Room>
     <Room :roomName="'Laza Lazarevic'" :events="events.LazaLazarevic"
     :deleteEvent="deleteEvent"
     ></Room>
  </div>
</template>

<script>
import Room from '@/components/Room';

export default {
    name: 'Schedule',
    methods: {
        deleteEvent(eventId, roomName) {
            const camelCaseRoomName = this.stringToCamelCase(roomName);

            this.events[camelCaseRoomName] = this.events[
                camelCaseRoomName
            ].filter(event => event.id !== eventId);
        },

        stringToCamelCase(str) {
            return str.replace(/\W+(.)/g, (match, chr) => chr.toUpperCase());
        }
    },
    components: {
        Room
    },
    data() {
        return {
            events: {
                MilutinMilankovic: [
                    {
                        id: 0,
                        name: 'Daily Standup',
                        startTime: '09:30',
                        endTime: '10:00'
                    },
                    {
                        id: 1,
                        name: 'JavaScript Interview',
                        startTime: '14:30',
                        endTime: '15:30'
                    }
                ],
                LazaLazarevic: [
                    {
                        id: 0,
                        name: 'Best Vue introduction',
                        startTime: '11:00',
                        endTime: '12:00'
                    },
                    {
                        id: 1,
                        name: 'Chill',
                        startTime: '12:00',
                        endTime: '17:00'
                    }
                ]
            }
        };
    }
};
</script>

<style lang="scss">
.schedule {
    display: flex;
    flex-direction: row;
    width: 100%;
    justify-content: center;
    align-items: center;
}
</style>
