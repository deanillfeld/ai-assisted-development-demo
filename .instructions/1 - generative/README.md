# Setup
1. Ensure that the Github Copilot extension is installed and logged in
2. Ensure Copilot is in edit mode
3. Ensure Sonnet 4 is selected as the LLM to use

# Workflow
1. We will implement https://github.com/deanillfeld/ai-assisted-development-demo/issues/1
2. Develop a plan, save it to a file and then have Copilot execute it in Edit mode
3. Test the application
4. Resolve any issues
5. Raise a PR but do not merge it.

# Talking Points
1. We'll start with a generative AI workflow. This style of workflows were the most common way of interacting with AI's up until recently.

2. The LLM completed the task, but you had to do all the legwork yourself. You needed to go read the github issue, copy paste it into VScode then you needed to run all the commands to install depedenceies yourself.

3. There isnt a complete feedback loop, the LLM cant know if what it wrote on its first try even works. You need to go install any dependencies, run the tests and then provide the LLM with explicit feedback to fix any issues and then try again.

4. What if there was a more efficient way that didnt require you to be the gopher and do all the legwork for the LLM? Introducing Agentic AI.