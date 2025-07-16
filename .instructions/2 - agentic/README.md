# Setup
1. Ensure that the Github Copilot extension is installed and logged in
2. Ensure Copilot is in agent mode
3. Ensure Sonnet 4 is selected as the LLM to use
4. Add the Github MCP in remote mode
5. Ensure the vscode terminal integration works. Ask Copilot to test it out.

# Workflow
1. We will implement https://github.com/deanillfeld/ai-assisted-development-demo/issues/1
2. Develop a plan, save it to a file and then have Copilot execute it.
3. Have copilot iterate on its own through the code -> test -> fix cycle.
4. Have copilot raise a PR.

# Talking Points
1. Explain what Agentic AI actually is and how its different to Generative AI

2. Show how the Github MCP server allows us to directly access the Github API from our LLM, we no longer have to copy paste it into the chat interface.

3. Github isnt the only MCP server out there, almost everything has an MCP server available in varying stages of completeness. You could have your LLM directly read from another repository, a confluence space, or even a website. Which is very useful in software development as libraries change on a daily basis and sometimes you will need more up to date documentation than what the model saw when it was trained.

4. Show how the feedback loop is now complete, allowing the LLM to make a code change, then run the tests, fix any thing that it didnt get right on the first try and then rinse and repeat. You no longer need to be in the middle explaining what the LLM got wrong.

5. Show how you still have control and shouldnt just blindly trust the LLM, show how you can have it only work on 1 piece at a time rather than completing every step at once which is hard to follow.

6. Show how you have control over what commands it runs, or API calls it makes. However in the interest of speed you also have the ability to tell the LLM it has free reign to use a tool without your approval. 