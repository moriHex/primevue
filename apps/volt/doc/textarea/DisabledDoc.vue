<template>
    <DocSectionText v-bind="$attrs">
        <p>When <i>disabled</i> is present, the element cannot be edited and focused.</p>
    </DocSectionText>
    <div class="card flex justify-center">
        <Textarea v-model="value" rows="5" cols="30" disabled class="resize-none" />
    </div>
    <DocSectionCode :code="code" />
</template>

<script setup lang="ts">
import Textarea from '@/volt/Textarea.vue';
import { ref } from 'vue';

const value = ref(null);

const code = ref(`
<template>
    <div class="card flex justify-center">
        <Textarea v-model="value" rows="5" cols="30" disabled class="resize-none" />
    </div>
</template>

<script setup lang="ts">
import Textarea from '@/volt/Textarea.vue';
import { ref } from 'vue';

const value = ref(null);
<\/script>
`);
</script>
