# Todo-To-Asana
Get any new TODO/FIXME comments then send them to Asana as a new ticket.

## Variables
 - `github-token`
   - Required
   - Used to get info about pull request.
   - Just pass `"${{ secrets.GITHUB_TOKEN }}"` 
 - `asana-pat`
   - Required
   - Used to interface with Asana
   - Create a new Personal Access Token (PAT) via this [link](https://developers.asana.com/docs/personal-access-token)
 - `asana-projects`
   - Required
   - Projects that the new ticket will be added. Need at least one but can have several. Each must be separated by comma only (no space etc.) 
 - `code-language`
   - Not required
   - Used to determine the Regex used to search for TODO comments
   - If not set will use the language from Github Context
   - Can be set to "default" and will try to catch comments widely

## Triggers
 - Requires pull request information so set `on:` to be `pull_request` and `types:` can be something like `[opened]` or `[ready_for_review]` or `[closed]`.
 - If on is not set to pull_request and error will be thrown.
 - Having different types might cause the same tasks to be generated multiple times.
 - To run when a pull request is successfully merged set the types to `[closed]` an add the following line `if: github.event.pull_request.merged == true`

## Sample Yaml files
![スクリーンショット 2024-04-10 11 59 35](https://github.com/zaburen/todo-to-asana/assets/108658635/e01b36cd-92f5-40a4-be00-57b57de5aba3)

![スクリーンショット 2024-04-10 12 09 06](https://github.com/zaburen/todo-to-asana/assets/108658635/3fe445e9-18ec-4535-bc82-ad79ba2e0e22)

![スクリーンショット 2024-04-18 12 36 08](https://github.com/zaburen/todo-to-asana/assets/108658635/c9be8d57-0bdc-488d-9e76-60897e6f03c6)




