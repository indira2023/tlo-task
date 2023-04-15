In this lesson, we will apply our knowledge of JavaScript closures to create a simple Todo manager program.

The plan is as follows:

We will create a parent(in context of closure) todoList function.
Inside the todoList function, we will define two children functions namely add and markAsComplete to perform the respective operations.
Lastly, we will make sure that the todoList function returns the list of all todos along with the add and markAsComplete functions.

The implementation is as follows:
In this lesson, we will make use of the Node.js REPL. For this, we will open the terminal and run the node command to go inside the REPL mode.

So, let's get started.

First, we will define the todoList function.

const todoList = () =>
all = []
Here, we will keep the list of all todos inside the all array. A Todo will have three properties: title (of type String), dueDate(of type string), and completed (of type boolean). And inside the all array, we will store Todos as objects.
For example, { title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }.

Next, let's define the add() function.

const todoList = () => {
all = []
const add = (todoTask) => {
all.push(todoTask)
console.log(all)
}
}
The add() function takes a todoTask as an argument, and pushes into the all array.

Similarly, we will define the markAsComplete() function.

const todoList = () => {
all = []
const add = (todoTask) => {
all.push(todoTask)
console.log(all)
}
const markAsComplete = (index) => {
all[index].completed = true
console.log(all)
}
}
Here, the markAsComplete() function takes an argument called index. It updates the all array using the index, and marks that specific Todo as completed.

To complete the todoList function, we will return the all array and add, markAsComplete functions.

const todoList = () => {
all = []
const add = (todoTask) => {
all.push(todoTask)
console.log(all)
}
const markAsComplete = (index) => {
all[index].completed = true
console.log(all)
}
return { all, add, markAsComplete };
}
Let us test this code.
First, in the terminal, we will call the todoList() function.

> const todos = todoList()
> Now, you will be able to see the list of all todos by:

> todos.all
> [] // It will return an empty array
> To add a new Todo:

> todos.add({ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false })
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }] // Output
> todos.add({ title: 'Have to buy potato', dueDate: '22-06-2022', completed: false })
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: false }] // Output
> todos.all
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: false }] // Output
> To mark a Todo as complete

> todos.markAsComplete(1) // Here 1 is the array index
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: true }] // Output
> So, it's working!

As we've learned before, in this example, the two functions add and markAsComplete have preserved the legacy variable all when the todoList() function was executed, and continued to preserve(closure) it.

