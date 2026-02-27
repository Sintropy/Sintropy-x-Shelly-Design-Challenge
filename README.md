# Sintropy x Shelly – Design Challenge

## Objective

We want to integrate a **Shelly devices module** into the **Sintropy** platform using our APIs.

⚠️ This challenge is focused on **reasoning**, not on code.  
We will not compile or execute anything.  
We are interested in understanding **how you think**, how you structure a problem, and how you explain your decisions.

---

## Context

Assume Sintropy APIs are:

- **Multi-tenant** (multiple customers use the system in isolation)
- Protected by an existing authentication layer that allows identifying which tenant is requesting a resource  
- Authentication/authorization design is **not part of this test**

You can assume that when a request reaches your module, the tenant is already identified.

---

## Documentation

- Sintropy API: https://sintropy.ai/api-docs  
- Shelly API: https://shelly-api-docs.shelly.cloud/

Regarding the Shelly documentation:

👉 **Ignore the "Cloud API / API Integrator" section.**  
For this challenge, focus only on APIs relevant to:
- reading device data
- reading ON/OFF state
- sending ON/OFF commands

You do not need to study everything in detail — use only what is relevant.

---

## Scope of the Challenge

For simplicity, imagine we need to manage a generic category of Shelly devices that:

- produce electrical measurements (e.g. voltage and current)
- expose an ON/OFF state and can be switched on or off

The specific device model is not important.  
The goal is to reason about how you would abstract this type of device within Sintropy APIs.

We conceptually treat devices as:

- **sensors** generating data (voltage/current)
- **actuators** exposing a modifiable state (ON/OFF)

⚠️ Important note:  
The ON/OFF command may also be triggered manually (e.g. physical button or operator).  
The system must therefore be able to read and maintain an **updated device state**.

Out of scope:

- UI
- provisioning account
- deployment or infrastructure setup
- real database implementation
- support for all Shelly models

If something is unclear, make reasonable assumptions and state them explicitly.

---

## Scale Scenario

Consider a scenario with **100 customers**, each with **100 devices** (around **10,000 devices** total).

**Reason about how to keep the ON/OFF state exposed by Sintropy APIs as up-to-date as possible over time, while avoiding approaches that may not scale well as the number of devices grows.**

Additionally:

- Assume external APIs (Shelly) may not always be available. How would you handle this?
- Explain what you consider to be “up-to-date state” and what trade-offs you would accept between accuracy and scalability.

---

## What We Ask You To Do

Imagine you are designing this integration.

Describe:

1. How you would model devices inside Sintropy (multi-tenant aware)
2. How you would expose voltage/current data and ON/OFF state via API
3. How you would send ON/OFF commands through Sintropy APIs
4. How you would handle state changes triggered manually
5. How you would handle temporary unavailability of Shelly APIs
6. Potential issues or edge cases you foresee

There is no single correct answer.  
We care more about your reasoning than about a perfect solution.

---

## Deliverable

Create a private repository using this template and add us as collaborators.

Inside your repository, create a file:

`SOLUTION.md`

Include:

- Your assumptions
- A proposed architecture (can be simple)
- Example API endpoints with JSON examples
- Explanation of your decisions
- Alternative approaches you considered
- (Optional) A section titled “Bonus – AWS”

You may use:

- Text explanations
- Bullet points
- JSON examples
- Pseudocode
- Simple diagrams (ASCII or Mermaid)

🚫 Do not write executable code.  
We prefer a clear explanation in `SOLUTION.md` over working code.

---

## Evaluation Criteria

We evaluate:

- Clarity of reasoning
- Ability to structure the problem
- Consistency between APIs, tenant model, device state, and behavior
- Ability to identify scalability and availability concerns
- Ability to reason about trade-offs
- Technical communication

We do NOT evaluate:

- Executable or working code
- Implementation completeness
- Language or framework choice
- Diagram aesthetics or formatting
- Exact endpoint syntax precision
- Repository formatting or style

Use any format that best helps you explain your reasoning.

---

## Bonus (Optional) – AWS

This section is optional.

If you are familiar with AWS (even at a basic level), briefly answer the following.  
If not, ignore this section — it will not affect your evaluation.

**Question:**  
Ignoring the Shelly integration, how would you design Sintropy APIs using AWS services?

High-level answers are sufficient. For example:

- Which services would you use (API Gateway, Lambda, ECS, DynamoDB, SQS, EventBridge, etc.)
- How you would separate main components
- How you would handle authentication, logging, and persistence

Partial answers are perfectly fine — we just want to understand how you think.

---

## Time

Take the time you consider appropriate.  
We may discuss and explore your ideas together in a follow-up conversation.

---

## Submission

1. Click "Use this template"
2. Create a private repository in your account
3. Add the following GitHub users as collaborators:
   - `pietroparini2`
   - `CDNNDR`
4. Send us the repository link
