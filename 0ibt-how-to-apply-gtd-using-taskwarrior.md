# How to apply GTD using Taskwarrior
#tasks #gtd #howtodo #method

- First of tall you have to understand about the Inbox is where all the concepts/tasks/ideas that need to be processed goes
- The important thing here is that task only tasks that are necessary appears for the following command:
- ==tickle== = `task +in +tickle wait:+(d)d` is task that you want to think more about it or project not yet solid
- ==think== = `task +in +tickle wait+1d` is something you think, but does not take too long to appear for you next
- `task next` (This is the task you are really going to do on the day)
- First thing of the day you are going to process `task in`
    - If not actionable,
		- I can create another one using ==think== and `task -in` or
		- `task t delete ` if I do not want to think about this task/concept anymore
	- if actionable
		- is ==task== can be done with less than 2 minutes do it and `task t done`
		- defer: `task t done` and `task +next proj:p concrete_action`
		- delegate: `task t modify -in +waiting` and `task t annotate "zzzzzz"` and `task t modify due:+1w wait:+3d`
		- if task is `abstract` and more than 2 items can be created:
			- `task add +next pro:new.p "xxxxx"`
			- `task add +next pro:new.p "yyyyy"`
			- `task add +in "zzzzz"`
- See which task now need to be done using `task next` and take it one by one
