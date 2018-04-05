<template>
  <div id="app" class="min-h-screen text-black bg-grey-lighter p-8">
    <div class="bg-white rounded shadow-lg max-w-md mx-auto py-8 px-4">

      <sortable-list v-model="todos">
        <ul class="list-reset" slot-scope="{ items }">
          <sortable-item v-for="todo in items" :key="todo.id">
            <li class="bg-white px-4">
              <div class="flex items-center border-b border-grey-lighter">
                <div class="flex-grow flex items-center py-4">
                  <input type="checkbox" v-model="todo.complete" class="mr-3">
                    <span>{{ todo.description }}</span>
                </div>
                  <sortable-handle>
                    <svg class="ml-2 h-4 w-4 cursor-move text-grey hover:text-grey-darkest" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor"><path fill-rule="evenodd" d="M14 4h2a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1h-2a1 1 0 0 1-1-1V5a1 1 0 0 1 1-1zM8 4h2a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1H8a1 1 0 0 1-1-1V5a1 1 0 0 1 1-1zm6 6h2a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1h-2a1 1 0 0 1-1-1v-2a1 1 0 0 1 1-1zm-6 0h2a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1H8a1 1 0 0 1-1-1v-2a1 1 0 0 1 1-1zm6 6h2a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1h-2a1 1 0 0 1-1-1v-2a1 1 0 0 1 1-1zm-6 0h2a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1H8a1 1 0 0 1-1-1v-2a1 1 0 0 1 1-1z"/></svg>
                  </sortable-handle>
              </div>
            </li>
          </sortable-item>
        </ul>
      </sortable-list>

    </div>
  </div>
</template>

<script>
import SortableList from './components/SortableList'
import SortableItem from './components/SortableItem'
import SortableHandle from './components/SortableHandle'

export default {
  name: 'app',
  components: {
    SortableList,
    SortableItem,
    SortableHandle,
  },
  data() {
    return {
      todos: [
        { id: 1, description: "Get travel insurance", complete: false },
        { id: 2, description: "Pay hydro bill", complete: false },
        { id: 3, description: "Record podcast with Taylor", complete: false },
        { id: 4, description: "Design Twitter card for new landing page", complete: false },
        { id: 5, description: "Update credit card for Typekit subscription", complete: false },
      ],
    }
  },
}
</script>

<style>
@import "tailwindcss/preflight";
@import "tailwindcss/components";
@import "tailwindcss/utilities";
</style>
