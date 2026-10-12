<h1>Todo List</h1>

{#each tasks as task}
  <div>
    <p>{task}</p>
  </div>
{/each}

<button on:click={AddTask}>Add Task</button>

<script>
  let tasks = [];

  function AddTask() {
    const newTask = prompt("Enter a new task: ");
    
    if (newTask) {
      tasks = [...tasks, newTask];
    }
  }
</script>
