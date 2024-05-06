# Muhammad Sean Arsha Galant 2206822963 - Tutorial 10 Part 1
## Reflection

## Experiment 1.2: Understanding how it works.
![Screenshot 2024-05-06 092754.png](assets%2FScreenshot%202024-05-06%20092754.png)

When the program is ran, it starts by initializing an executor and a spawner. Then, it spawns a task that prints "howdy!" and waits for two seconds using the TimerFuture. Meanwhile, the main thread continues and prints "hey hey". After spawning the task, the spawner is dropped, signaling to the executor that no more tasks will be added. Next, the executor begins processing tasks from the queue. It receives the previously spawned task, prints "howdy!", waits for two seconds, and then prints "done!". Since there are no more tasks in the queue, the executor completes its execution. Consequently, the output that is observed is "hey hey" first, followed by "howdy!" after a brief pause of two seconds, and finally "done!". This sequence reflects the chronological execution of tasks in the program, demonstrating the asynchronous behavior facilitated by the executor and spawner.

## Experiment 1.3: Multiple Spawn and removing drop

### With Spawner
![alt text](<assets/Screenshot 2024-05-06 094812.png>)

### Without Spawner
![alt text](<assets/Screenshot 2024-05-06 094807.png>)
![alt text](<assets/Screenshot 2024-05-06 094901.png>)

In the first scenario, where drop(spawner) is included, the program runs without errors. This is because dropping the spawner signals to the executor that no more tasks will be added. Therefore, after spawning all tasks, the executor processes them sequentially, printing each "howdy!" message, waiting for two seconds, and then printing the corresponding "done!" message. Finally, the program terminates gracefully.
However, in the second scenario, where drop(spawner) is removed, the program runs into an issue. Without dropping the spawner, the executor keeps waiting for more tasks to be added indefinitely. As a result, although the tasks are executed and their corresponding "howdy!" and "done!" messages are printed, the program doesn't terminate on its own.

