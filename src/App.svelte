<script>
  let todos = [];

  let addTodo = () => {
    todos = [...todos, ""];
  };

  let removeSelf = (index) => {
    todos = [...todos.slice(0, index), ...todos.slice(index + 1)];
  };
</script>

<div class="todos">
  {#each todos as todo, index}
    <input
      type="text"
      class="todo"
      bind:value={todos[index]}
      placeholder="new todo"
    />
    <button on:click={() => removeSelf(index)}>remove</button>
    <br />
  {/each}
</div>
<button on:click={addTodo}>Add</button>

<style>
</style>
