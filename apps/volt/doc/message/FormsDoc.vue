<template>
    <DocSectionText v-bind="$attrs">
        <p>Validation errors in a form are displayed with the <i>error</i> severity.</p>
    </DocSectionText>
    <div class="card flex justify-center">
        <div class="flex flex-col gap-4">
            <Message v-if="!username || !email" severity="error" icon="pi pi-times-circle" class="mb-2">Validation error</Message>
            <Message v-if="username && email" severity="success" icon="pi pi-times-circle" class="mb-2">Form is valid</Message>
            <div class="flex flex-col gap-1">
                <InputText v-model="username" placeholder="Username" aria-label="username" :invalid="!username" />
                <Message v-if="!username" severity="error" variant="simple" size="small">Username is required</Message>
            </div>
            <div class="flex flex-col gap-1">
                <InputText v-model="email" placeholder="Email" aria-label="email" :invalid="!email" />
                <Message v-if="!email" severity="error" variant="simple" size="small">Email is not valid</Message>
            </div>
        </div>
    </div>
    <DocSectionCode :code="code" />
</template>

<script setup lang="ts">
import InputText from '@/volt/InputText.vue';
import Message from '@/volt/Message.vue';
import { ref } from 'vue';

const username = ref(null);
const email = ref(null);

const code = ref(`
<template>
    <div class="card flex justify-center">
        <div class="flex flex-col gap-4">
            <Message v-if="!username || !email" severity="error" icon="pi pi-times-circle" class="mb-2">Validation error</Message>
            <Message v-if="username && email" severity="success" icon="pi pi-times-circle" class="mb-2">Form is valid</Message>
            <div class="flex flex-col gap-1">
                <InputText v-model="username" placeholder="Username" aria-label="username" :invalid="!username" />
                <Message v-if="!username" severity="error" variant="simple" size="small">Username is required</Message>
            </div>
            <div class="flex flex-col gap-1">
                <InputText v-model="email" placeholder="Email" aria-label="email" :invalid="!email" />
                <Message v-if="!email" severity="error" variant="simple" size="small">Email is not valid</Message>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import InputText from '@/volt/InputText.vue';
import Message from '@/volt/Message.vue';
import { ref } from 'vue';

const username = ref(null);
const email = ref(null);
<\/script>
`);
</script>
