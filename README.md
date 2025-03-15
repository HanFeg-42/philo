# philo
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Philosopher's Problem Simulation</title>
</head>
<body>

<h1>Philosopher's Problem Simulation</h1>

<p>This project simulates the classic "Dining Philosophers" problem using threads and mutexes. It models a scenario where philosophers sit at a round table, with a bowl of spaghetti and a fork between each pair of philosophers. Each philosopher alternates between eating, thinking, and sleeping.</p>

<h2>Key aspects of the simulation are as follows:</h2>
<ul>
    <li><strong>Philosophers</strong>: Each philosopher is represented by a separate thread. They need to eat, think, and sleep, but they can only eat when holding both the left and right forks.</li>
    <li><strong>Forks</strong>: There are as many forks as there are philosophers, and each philosopher holds one fork on their left and one on their right while eating. The forks are protected with mutexes to avoid conflicts.</li>
    <li><strong>State Transitions</strong>: Philosophers go through various states: thinking, eating, sleeping, and dying. The state changes must be logged with a timestamp in the format:
        <ul>
            <li>timestamp_in_ms X has taken a fork</li>
            <li>timestamp_in_ms X is eating</li>
            <li>timestamp_in_ms X is sleeping</li>
            <li>timestamp_in_ms X is thinking</li>
            <li>timestamp_in_ms X died</li>
        </ul>
    </li>
    <li><strong>Simulation Rules</strong>: Philosophers must not starve. The simulation stops when either a philosopher dies from starvation or when all philosophers have eaten a specified number of times (if provided).</li>
</ul>

<h2>Project Structure</h2>
<ul>
    <li><strong>philo.c</strong>: The main program implementing the simulation logic.</li>
    <li><strong>philo.h</strong>: Header file containing necessary function prototypes and structure definitions.</li>
    <li><strong>Makefile</strong>: Used for compiling and managing the build process.</li>
</ul>

<h2>Requirements</h2>
<ul>
    <li>The program must compile without errors and correctly simulate the philosophers’ behavior.</li>
    <li>Each philosopher should eat at least once before the simulation ends, and they must not starve.</li>
    <li>State transitions must be logged with precise timestamps.</li>
</ul>

<h2>Key Functions Used:</h2>
<ul>
    <li><code>pthread_create</code>, <code>pthread_detach</code>, <code>pthread_join</code> for managing threads.</li>
    <li><code>pthread_mutex_init</code>, <code>pthread_mutex_lock</code>, <code>pthread_mutex_unlock</code> for managing mutexes to protect shared resources (forks).</li>
    <li><code>usleep</code> for simulating sleep behavior and creating pauses between actions.</li>
</ul>

<h2>Compilation:</h2>
<p>To compile and run the program, use the provided Makefile with the following commands:</p>
<ul>
    <li><code>make</code> to compile the program.</li>
    <li><code>make clean</code> to remove object files.</li>
    <li><code>make fclean</code> to remove all compiled files.</li>
    <li><code>make re</code> to recompile the project.</li>
</ul>

</body>
</html>
