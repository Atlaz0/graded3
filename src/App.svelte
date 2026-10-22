<h1>Todo List</h1>

{#each tasks as task, index}
  <div class="task-item">
    <p>{task}</p>
    <button on:click={() => RemoveTask(index)}>Remove Task</button>
  </div>
{/each}

<button class="add-btn" on:click={AddTask}>Add Task</button>

<script>
  let tasks = [];

  function AddTask() {
    const newTask = prompt("Enter a new task: ");
    
    if (newTask) {
      tasks = [...tasks, newTask];
    }
  }

  function RemoveTask(indexToRemove) {
    tasks = tasks.filter((_, index) => index !== indexToRemove);
  }
</script>

<style>
  .task-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 300px;
    margin-bottom: 10px;
    padding: 8px;
    background: #f4f4f4;
    border-radius: 4px;
  }

  .task-item p {
    margin: 0;
  }

  .add-btn {
    margin-top: 10px;
  }
</style>
