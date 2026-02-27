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
- Protected by an existing authentication layer that identifies which tenant is requesting a resource
- Authentication/authorization design is **not part of this test**

You can assume that when a request reaches your module, the tenant is already identified.

---

## Documentation

- Sintropy API: https://sintropy.ai/api-docs  
- Shelly API: https://shelly-api-docs.shelly.cloud/

Regarding the Shelly documentation:

👉 Ignore the section related to **API Integrator**.

For this challenge, focus only on APIs relevant to:

- Retrieving device data  
- Retrieving device state  
- Receiving state updates (if applicable)  
- Sending ON/OFF commands  

You are free to choose the integration approach you consider most appropriate.

---

## Scope of the Challenge

We consider devices that:

- Produce electrical measurements (voltage/current)
- Expose an ON/OFF state that can be modified

The specific device model is not relevant.  
Reason in terms of abstraction.

⚠️ The ON/OFF state may also change manually (e.g. physical button).  
The system must maintain an **updated device state**.

---

## Scale Scenario

Consider a scenario with **100 customers**, each with **100 devices** (around **10,000 devices** total).

**Reason about how to keep the ON/OFF state exposed by Sintropy APIs as up-to-date as possible over time, while avoiding approaches that may not scale well as the number of devices grows.**

Additionally:

- Assume external APIs (Shelly) may not always be available — how would you handle this?
- Explain what you consider to be “up-to-date state” and what trade-offs you would accept between accuracy and scalability.

---

## What We Ask You To Do

Describe:

1. How you would model devices (multi-tenant aware)
2. How you would expose telemetry and ON/OFF state via API
3. How you would send ON/OFF commands
4. How you would handle manual state changes
5. How you would handle temporary unavailability of Shelly APIs
6. Any edge cases you foresee

There is no single correct answer.  
We care more about your reasoning than about a perfect solution.

---

## Deliverable

Create a private repository using this template and add us as collaborators.

Create a file:

`SOLUTION.md`

Include:

- Your assumptions
- Proposed architecture
- Example API endpoints (JSON examples are sufficient)
- Explanation of your decisions
- Trade-offs considered

### Format

You are free to use **any format** that helps you clearly explain your reasoning:

- Plain text
- Bullet points
- JSON examples
- Pseudocode
- Simple diagrams (ASCII or Mermaid)
- Mixed structure

🚫 Do not write executable or production-ready code.  
We are evaluating reasoning and clarity only.

---

## Evaluation Criteria

We evaluate:

- Clarity of reasoning
- Problem structuring ability
- Consistency between APIs, tenant model, and device state
- Scalability and availability awareness
- Ability to reason about trade-offs
- Technical communication

We do NOT evaluate:

- Working code
- Implementation completeness
- Language/framework choice
- Diagram aesthetics
- Repository formatting

---

## Bonus (Optional) – AWS

This section is optional.

If you are familiar with AWS (even at a basic level), briefly answer the following.  
If you are not, ignore this section — it will not affect your evaluation.

**Question:**  
Ignoring the Shelly integration, how would you design Sintropy APIs using AWS services?

High-level thinking is sufficient. For example:

- Which services would you use? (e.g. API Gateway, Lambda, ECS, DynamoDB, SQS, EventBridge, etc.)
- How would you separate main components?
- How would you handle authentication, logging, and persistence?
- Would you use an event-driven approach? Why?

You may answer in a short section inside `SOLUTION.md` titled:

`Bonus – AWS`

Even a partial answer is perfectly fine — we are interested in how you reason about system design.

---

## Time

Take the time you consider appropriate.  
We may discuss your ideas together in a follow-up conversation.

---

## Submission

1. Click "Use this template"
2. Create a private repository
3. Add the following GitHub users as collaborators:
   - `pietroparini2`
   - `CDNNDR`
4. Send us the repository link
