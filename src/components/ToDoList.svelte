<script>
    let todos = $state([
        { title: "Assignment 1", done: false },
        { title: "Assignment 2", done: false },
        { title: "Assignment 3", done: false }
    ]); //è un array di oggetti, ogni oggetto rappresenta un to do con un titolo e un booleano che indica se è stato fatto o no 
</script>

<h3>My Todos</h3>

<ul>
    {#each todos as todo} <!--per ogni elemento dell'array todos, creo un elemento li con il titolo del to do e una checkbox che indica se è stato fatto o no--> 
        <li>
            <input type="checkbox" bind:checked={todo.done}> <!--grazie al bind, quando cambio lo stato della checkbox, cambia anche il valore di done del to do corrispondente-->
            {todo.title}</li>
    {/each}         
</ul>