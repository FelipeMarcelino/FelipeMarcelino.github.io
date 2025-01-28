# How to use Taskwarrior to apply GTD

#gtd #taskwarrior #methodology

## Tags

- `+in` = inbox
- `+wating` = waiting list
- `+next` = next action list

## commands

- `in` = `task add +in`
- `tickle` = `task add +in wait:$deadline`
- `think` = `tickle +1d`

## Workflow

- Add ideas into inbox using `in` command whenever you remember them
  - This ideas come from email, small papers, social medias and etc.
  - They will be processed when you open your inbox

- Open the `inbox` with all ideas with tag `+in`.
  - On inbox I will have `incubated` things that came from the `thickle` and
    `think` command
  - Analyze the idea and see if if this is **actionable**

- **Item is not a action item** you can `think` about it or we can `tickle` it
  for some specific day. Simply delete it if you think it is not important
  anymore
  - Maybe we can simulate someday/maybe with `tickle` command with longest dates
    or will be better to have `+someday` tag in that case

- **Item is a action**
  - One action:
    - Less than 2 minutes: **Do it**
    - Bigger than 2 minutes:
      - **Delegate** remove `+in` tag and add `+waiting` tag and add `due` date
        and maybe `wait` date
      - **Defer**
        - Defer item to a specific project and see if the task is the next
          action of the project
          - Is it possible that this action is not the `+next` action of the
            project?
          - All the tasks are inside in a specific project?
          - Can you defer to a specific date and this action receive `+next`
            tag?
  - More actions:
    - Add multiple concrete actions to a specific project
      - All of this actions receive the tag `+next`?
    - Create one action indicating the continuation of the project ?
      - This action receive the tag `+in` because it will be the action that
        will be the starting point of the second set of the concrete actions

## Weekly Review

- Review the `+waiting` tasks and see if they are done
- See the `-next` actions from projects and see if you can add the tag `+next`
  to one of them itens
  - A project need to have at least one item with `+next` tag
- Is that situation that I will review the items with the tag `+someday` that
  comes from the `inbox`?

## Sources

- [[blog/2025-01-26]]
- [[blog/2025-01-25]]
- [Reddit 1](https://www.reddit.com/r/gtd/comments/1769pgz/question_about_scheduling_and_next_actions/)
