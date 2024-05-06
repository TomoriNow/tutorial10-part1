# Muhammad Sean Arsha Galant 2206822963 - Tutorial 10 Part 1
## Reflection

## Experiment 1.2: Understanding how it works.
![Screenshot 2024-05-06 092754.png](assets%2FScreenshot%202024-05-06%20092754.png)

When the program is ran, it starts by initializing an executor and a spawner. Then, it spawns a task that prints "howdy!" and waits for two seconds using the TimerFuture. Meanwhile, the main thread continues and prints "hey hey". After spawning the task, the spawner is dropped, signaling to the executor that no more tasks will be added. Next, the executor begins processing tasks from the queue. It receives the previously spawned task, prints "howdy!", waits for two seconds, and then prints "done!". Since there are no more tasks in the queue, the executor completes its execution. Consequently, the output that is observed is "hey hey" first, followed by "howdy!" after a brief pause of two seconds, and finally "done!". This sequence reflects the chronological execution of tasks in the program, demonstrating the asynchronous behavior facilitated by the executor and spawner.


