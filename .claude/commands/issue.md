Analyze and fix the GitHub issue: $ARGUMENTS.

Follow these steps:

# PLAN
1. Use 'gh issue view' to get the issue details
2. Understand the problem described in the issue
3. Ask clarifying questions if necessary
4. If the issue does not require code changes, skip to CREATE, else continue with the instructions.
5. Understand prior art for the issue
- Search the scratchpads for previous thoughts related to the issue
- Search PRs to see if you can find history on this issue
- Search the codebase for relevant files
6. Think harder about how to break the issue down into a series of small, manageable tasks
7. Document your plan in a new scratchpad
- include the issue name in the filename
- include a link to the issue in the scracthpad

# CREATE
- Create a new branch for the issue
- Solve the issue in small, manageable steps, according to your plan
- Commit your changes after each step

# TEST
- If the issue does not require code changes, skip to DEPLOY, else continue with the instructions
- Use pupeteer via MCP to test the changes if you have made changes to the frontend
- Write unit tests of your code, respecting the folder structure
- Run the full test suite to ensure you haven't broken anything
- If the tests are failing, fix them
- Ensure that all tests are passing before moving on to the next step

# DEPLOY
- Open a PR and request a review

Remember to use the GitHub CLI ('gh') for all GitHub-related tasks

In the ISSUETRACKER.md file, add a short summary of the fix, no more than 1 line sentence. Format it as Issue-number_argument: short summary.