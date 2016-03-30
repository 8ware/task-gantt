
task-gantt
==========

Generating Gantt charts from Taskwarrior entries.

![`task-gantt status:pending pro:task-gantt`](doc/gantt.png)

The idea is to specify a `due` date and a `duration` (UDA) and then treat the
task as it would start at `due - duration` and end at `due` date.


Setup
-----

1.	Add `duration` as user defined attribute to your `~/.taskrc`

	```
	uda.duration.type = numeric
	```

2.	Install `Project::Gantt` perl module

	```
	cpanm Project::Gantt
	```


Usage
-----

```
task-gantt [--stdout] [-d <description>] [-o <filename>] <filters> ...
```
For example, to generate a Gantt chart of all pending tasks and watch it
directly with `feh` execute
```
task-gantt --stdout status:pending | feh -
```

