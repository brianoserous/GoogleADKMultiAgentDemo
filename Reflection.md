### Reflection - Google Web ADK Assignment - Brian Lilley



What changed when moving from single to multi-agent was the addition of sub\_agents with pointers to yaml 'config\_paths' in the root\_agent yaml definition.

Along with an additional instruction in the root agent's system prompt to classify and assign tasks to these specialist sub agents the system was then able to reason about the inbound requests and assign 'route' queries parsed from the users prompt.



The most helpful element in the signals under tracing was the request and response elements from each of the events such as LLM calls since it gave insight into the flow between agents and also what the makeup of the payload into and out of each agent is.  For example, the request event shows the system\_instruction along with the user prompt as it calls the llm.



By seeing the content of the request to the LLM I could also see the 'system\_instruction' and the 'tools: function\_declarations' for 'transfer\_to\_agent' elements which I assume are all log entries refelecting python constructs which had been automagically created when I defined the agent in the webADK. 



The Architectural improvement to Web ADK is that I would allow it expose the python files it has created in order to host the agents define.  I was unable to find the code.



Architectureal improvement to the application itself would of course be more detail in the root agent system prompt to tell it which council it worked for.











