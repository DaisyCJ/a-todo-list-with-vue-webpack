<template>
    <div>
        <baseInput
            v-model="newInput"
            placeholder="add an item"
            @keyup.enter="addItem"
            @add="addItem"
        />
        <ul v-if="items.length">
            <todoListItem
                v-for="item in items"
                :key="item.id"
                :content="item"
                @delete="removeItem"
            />
        </ul>
        <p v-else>
            Nothing left
        </p>
    </div>   
</template>

<script>
import baseInput from "./baseInput.vue"
import todoListItem from "./todoListItem"

let idNum = 1

export default {
    components: {
        baseInput, todoListItem
    },
    data () {
        return {
            newInput: '',
            items: [
                {
					id: idNum++,
					text: 'Learn Vue'
				},
				{
					id: idNum++,
					text: 'Learn about single-file components'
				}
            ]
        }
    },
    methods: {
        addItem: function() {
            if(this.newInput) {
                this.items.push({id: idNum++, text: this.newInput}),
                this.newInput = ''
            }
        },
        removeItem: function(index) {
            this.items = this.items.filter(item => {
                return index!=item.id
            })
        }
    }
}
</script>

