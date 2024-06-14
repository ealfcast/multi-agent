# Multi-agent Collaboration Solutions evaluation using Agents for Amazon Bedrock, BERT transformers
This workshop is built to help you learn about Multi-agent Collaboration using Agents for Amazon Bedrock.
The workshop helps builders easily create multiple agents, see how they can be used together to
accomplish tasks, and provide an environment for experimenting with different techniques and 
patterns related to multi-agent collaboration. Customers adopting agents at scale are looking for ways
to implement multi-agent collaboration, including ways to unify and simplify the experience for their
customers, and hiding the complexity of multi-step tasks that leverage a set of agents behind the scenes.

![Simplifying customer experience](multi-agent-collab.png)

The sample domain used is to deliver a chat experience for mortgage company. To keep things simple,
we start with two agents and one knowledge base:

- Agent for Existing Mortgages: an agent for customers to manage their existing mortgage.
- Agent for Mortgage Application Process: an agent for customers to create and complete a mortgage application.
- Knowledge Base for General Mortgage knowledge: a knowledge base with an understanding of different mortgage types,
their tradeoffs, and mortgage refinancing.

We build these agents and KB's, and we add a Supervisor Agent on top of them. The supervisor agent is able to
use its sub-agents and KB's to handle customer conversations with questions like:

1. What is my principal balance?
2. When is my next payment due?
3. What are the tradeoffs between 15-year and 30-year mortgages?
4. What other documents are needed to complete my new mortgage application?

The workshop is packaged as a set of notebooks:

- **01_create_agents_and_kbs:** creates the agents and knowledge bases and does simple validation of them in isolation.
- **02_supervisor_agent:** creates a supervisor agent that knows about the individual agents 
and knowledge base, and exercises the supervisor agent to demonstrate how it uses sub-agents, KB's, and even how it can control voice / tone of the output
and integrate guardrails to keep conversations from discussing selected topics, etc.
- **03_intent_classification:** provides an alternative pattern for leveraging sub-agents. It
uses an LLM prompt to do intent classification and then invokes the appropriate sub-agent
directly.
- **04_function_calling:** show how Bedrock function calling can help choose which sub-agent
to call, and the client can provide its own orchestration.
- **05_agent_evaluation:** shows how to test and evaluate agents.

A pair of helper classes ('AgentsForAmazonBedrock', and 'KnowledgeBase') are provided to
simplify creation, deletion, and invocation of Agents, Supervisor Agents, and Knowledge Bases.
