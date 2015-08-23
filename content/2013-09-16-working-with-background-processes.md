Title: Working with Background Processes
Date: 2013-09-16 21:33
Modified: 2015-03-24 13:38
Category: Programming
Tags: unix

For long running processes, rather than blocking your prompt, it's often useful to push commands to the background and complete other tasks.

To run a command in the background.

```bash
<command> &
```

With `nohup` you can run a command which will continue after logout.  It will ignore SIGHUP signals. `nice` sets a lower priority.

```bash
nohup nice <command> &
```

With `screen` you can run a command which can be resumed after logout.  It creates a new window with multiple processes instead of multiple Unix login sessions, so it is resource efficient.

```bash
screen -A -m -d -S mysessionname ./myscript.sh &
```

List all background processes

```bash
jobs
```

To send currently running command to background, first stop the process, `Ctrl-z`.

```bash
bg
```

To bring a background process to the foreground

```bash
fg
fg %1
```

To destroy a background process

```bash
kill %1
kill -9 %1
kill <pid>
```

To receive an email notification when a background process finishes

```bash
<command> | tee command.log | mailx -s 'PROCESS COMPLETE' test@example.com &
```

To run a set of jobs when cpu levels permit, use batch.  <kbd>ctrl</kbd>+<kbd>d</kbd> to end input.

```bash
user@example.com > ~/.forward
batch -m
command1
command2
command3
```

You can list batch jobs and kill using the id

```bash
at -l
at -r id
```

