# CS5150 Software Engineering

Software engineering is what happens when software becomes too important to treat casually. The same field that gives us the Linux kernel, open collaboration, and SQLite with roughly `640x` more test code than production code is also the field shaped by failures like Therac-25, the FAA Advanced Automation System, Ariane 5, and the Boeing 737 MAX. Software can save time, scale to millions, and support entire organizations, but when it is built without the right discipline, the cost is delay, waste, broken systems, and sometimes real harm. That is the story of this course: software is powerful, the stakes are high, and engineering is how we build systems people can trust.

## Lecture 2

### Stakeholders

Stakeholders are the people or groups who affect the project or are affected by it.

| Stakeholder | What they care about |
| --- | --- |
| Developer | Buildability, maintainability, technical feasibility |
| Client | Cost, schedule, priorities, success of the project |
| Customer | Whether the software is worth buying or adopting |
| User | Usability, usefulness, reliability |
| Society | Safety, privacy, fairness, legal/ethical impact |

### Key ideas

- The first step in a project is identifying stakeholders.
- Stakeholder interests are often different.
- The `client` usually sets priorities because the client bears the cost and risk.
- Good software engineering reduces risk through communication and visibility.

### Quick example

For Canvas:

- Developer: Instructure engineers
- Client: Cornell or the organization paying for the service
- Customer: Cornell / university administration
- User: students, instructors, TAs
- Society: anyone affected by accessibility, privacy, or policy decisions

### Process Models

There is no single best process model. The right one depends on how stable the requirements are, how risky the project is, and how often feedback is needed.

### Fast comparison

| Model | Best when | Pros | Cons |
| --- | --- | --- | --- |
| Waterfall | Requirements are stable and formal documentation matters | Clear phases, easy to manage, strong documentation | Bad at change, feedback comes late |
| Modified Waterfall | Requirements are mostly known, but some revision is expected | More realistic than pure waterfall, still structured | Still slow when requirements change a lot |
| Prototyping / Iterative Refinement | Requirements are unclear, especially UI/workflow | Early feedback, helps discover real needs | Prototype may be mistaken for final product |
| Incremental Delivery | Partial working features are useful | Users get value early, progress is visible | Needs strong architecture and testing |
| Agile / Scrum / XP | Requirements change often and feedback is frequent | Flexible, fast feedback, good visibility | Can become messy with weak discipline or poor docs |
| COTS / Integration | A standard solution already exists | Faster, less need to build from scratch | Less flexibility, integration/vendor issues |

### When to use which

| Situation | Good fit | Why |
| --- | --- | --- |
| Government or highly regulated system | Waterfall / Modified Waterfall | Stable requirements, approvals, traceability |
| New app with unclear user needs | Prototyping + Agile | Learn quickly from user feedback |
| Large system that can ship in stages | Incremental Delivery | Delivers useful pieces over time |
| Fast-moving product team | Agile / Scrum / XP | Handles changing priorities well |
| Common problem with existing tools | COTS / Integration | Reuse is cheaper than rebuilding |

### Intuition through examples

| Example | Likely process | Why |
| --- | --- | --- |
| Tax reporting system with fixed rules | Waterfall | Rules are stable and documentation matters |
| New student planner app | Prototyping + Agile | Users may not know what they want until they see it |
| E-commerce platform built feature by feature | Incremental Delivery | Browsing, cart, payments can ship in stages |
| Team improving a live web product every 2 weeks | Scrum / Agile | Frequent feedback and changing priorities |
| Company using Shopify instead of building a store | COTS / Integration | Existing solution is faster and cheaper |

### What to remember for the exam

- There is no universally best process model.
- The first step is to identify stakeholders.
- Different stakeholders care about different things.
- The client usually sets priorities because the client bears risk.
- Process choice depends on requirement stability, feedback needs, and project risk.
- Good answers justify `why` a process fits, not just `which` process to pick.

### One-line summary

Lecture 2 says: first understand `who the software is for`, then choose `how the team should build it`.

## Lecture 3

### Requirements

Requirements describe what the system must do and what constraints it must satisfy. If the requirements are wrong, even well-written code produces the wrong system.

### Main types

| Type | Meaning | Examples |
| --- | --- | --- |
| Functional | What the system does | Login, submit assignment, generate report |
| Non-functional | How well the system works or what constraints it must obey | Performance, security, reliability, scalability, legal compliance |

### Fast test

| Requirement | Type | Why |
| --- | --- | --- |
| Users can reset their password by email | Functional | A system feature |
| Password reset links expire in 15 minutes | Non-functional | Security constraint |
| The site supports 10,000 concurrent users | Non-functional | Scalability/performance |
| Instructors can publish grades to students | Functional | A system action |
| The app must comply with FERPA | Non-functional | Legal/compliance constraint |

### User stories

User stories are short, user-focused descriptions of value.

Format:

`As a [role], I want [goal], so that [reason].`

Example:

`As a project manager, I want to generate a status report so that I can share progress with stakeholders.`

### Requirements vs user stories

| Item | Best for | Limitation |
| --- | --- | --- |
| Requirement | Precision and completeness | Can be too formal for clients |
| User story | Communicating user value simply | Often not detailed enough by itself |

### What to remember for the exam

- Functional requirements describe `what` the system does.
- Non-functional requirements describe `how well` or `under what constraints` it does it.
- Non-functional requirements often drive architecture.
- User stories are useful, but they are not a full replacement for requirements.
- A permission rule like `only admins can delete users` is usually best treated as functional behavior.

### One-line summary

Lecture 3 says: after choosing a process, define `what the system must do` before arguing about implementation.

## Lecture 4

### Modeling

Modeling is about simplifying a system so you can understand, discuss, and design it clearly before coding. Different models show different views of the same system.

### Main model types

| Type | Focus | Good for |
| --- | --- | --- |
| External | System in its environment | Context and boundaries |
| Structural | How parts are organized | Classes, components, relationships |
| Interaction | How actors/components communicate | Use cases, sequence diagrams |
| Behavioral | How the system changes over time | State changes, workflows, activities |

### UML basics

| Diagram | Shows | Main elements |
| --- | --- | --- |
| Use Case | What actors want to do with the system | Actor, use case, `<<include>>`, `<<extend>>` |
| Sequence | Order of interactions over time | Actor, objects, lifelines, messages, returns, alt frame |
| Data Flow / Activity | Flow of work or data | Activity, data, start/end, transitions |
| Class | Static structure | Classes and relationships |
| State / Transition | How an object/system changes state | States, events, transitions |

### Key distinctions

| Concept | Meaning |
| --- | --- |
| `<<include>>` | Included use case always happens as part of the base use case |
| `<<extend>>` | Extended use case happens only sometimes |
| Sequence diagram | Best for showing message order |
| Class diagram | Best for showing structure, not time order |
| Behavioral model | Best for showing changes over time |

### When to use what

| Need | Best model |
| --- | --- |
| Show who interacts with the system | Use Case |
| Show the order of calls/messages | Sequence |
| Show workflow or process steps | Activity / Data Flow |
| Show classes and relationships | Class |
| Show system/object state changes | State / Transition |

### What to remember for the exam

- A model is a simplified view, not the real system.
- Different models answer different questions.
- Use case diagrams show actors and goals.
- Sequence diagrams show interaction order over time.
- Class diagrams show static structure.
- Behavioral models show workflow or state change.
- `<<include>>` means always; `<<extend>>` means sometimes.

### One-line summary

Lecture 4 says: before building the system, choose the right model to explain the right part of it.

## Lecture 5

### Planning

Planning is about deciding whether a project is feasible and how it can be completed within time, scope, and resource limits. For the exam, the most important part is `critical path analysis`.

### Core planning terms

| Term | Meaning |
| --- | --- |
| Feasibility | Whether the project should be done at all |
| Scope | What is included, excluded, and dependent on other systems |
| Milestone | A checkpoint showing progress |
| Deliverable | A work product handed to the client/team |
| Dependency | One activity must finish before another can start |
| Duration | Time needed for an activity |
| Slack | How much an activity can slip without delaying the project |
| Critical Path | The longest dependency path that determines total project duration |

### Deliverable vs milestone

| Item | Meaning | Examples |
| --- | --- | --- |
| Deliverable | Something produced for others | Report, demo, code, documentation |
| Milestone | A progress checkpoint | End of sprint, testing target reached |

### Critical path analysis

| Step | Rule |
| --- | --- |
| Draw the network | Use tasks, durations, and dependencies |
| Forward pass | `ES = max(predecessor EF)`, `EF = ES + duration` |
| Project duration | Earliest finish of the final node |
| Backward pass | `LF = min(successor LS)`, `LS = LF - duration` |
| Slack | `LS - ES` or `LF - EF` |
| Critical path | Activities with `0 slack` |

### What to remember

| Idea | Why it matters |
| --- | --- |
| Take the `max` on the forward pass | A task must wait for all predecessors |
| Take the `min` on the backward pass | You must satisfy the most restrictive successor |
| Critical path has zero slack | Delay there delays the whole project |
| Non-critical tasks can still slip a little | Their slack absorbs delay |

### Quick example

| Task | Depends on | Duration |
| --- | --- | --- |
| A | - | 3 |
| B | A | 4 |
| C | B | 2 |
| E | - | 5 |
| F | A, E | 3 |
| G | F | 3 |
| Finish | C, G | 0 |

Paths:

- `A -> B -> C = 9`
- `E -> F -> G = 11` with `F` waiting for both `A` and `E`

So:

- earliest project finish = `11`
- critical path = `E -> F -> G`

### Common exam mistakes

- Adding predecessor times instead of taking the `max`
- Forgetting that multiple dependencies mean “wait for all”
- Mixing up milestone and deliverable
- Thinking the visually longest path is always the critical path
- Forgetting that only zero-slack activities are on the critical path

### What to remember for the exam

- Planning is about scope, feasibility, resources, risks, and schedule.
- Critical path analysis finds the minimum possible project duration.
- Forward pass gives earliest times.
- Backward pass gives latest times.
- Slack shows scheduling flexibility.
- The critical path is the longest path and has zero slack.

### One-line summary

Lecture 5 says: good planning turns dependencies into a schedule, and critical path analysis tells you what actually controls the finish date.

## Lecture 6

### Architecture

Architecture is the high-level structure of the system. It sits between requirements and code and captures the major design decisions that shape how the system is built and maintained.

### Levels of abstraction

| Level | Focus |
| --- | --- |
| Requirements | High-level `what` |
| Architecture | Mid-level `what`, High-level `how` |
| System Design | Low-level `what`, Mid-level `how` |
| Code | Low-level `how` |

### Coupling and cohesion

| Concept | Meaning | Good / Bad |
| --- | --- | --- |
| Coupling | Dependencies between subsystems | Low is good |
| Cohesion | How strongly related the responsibilities inside a subsystem are | High is good |

### Why it matters

| Idea | Why it matters |
| --- | --- |
| Low coupling | Changing one subsystem should not break many others |
| High cohesion | Each subsystem should have a focused purpose |
| Simplicity | Easier to implement, test, maintain, and extend |

### What to remember for the exam

- Architecture is the high-level organization of the system.
- It sits between requirements and detailed design/code.
- Requirements focus on `what`; architecture focuses on the major `how`.
- Good architecture aims for `low coupling` and `high cohesion`.
- High coupling means changes spread across subsystems.
- High cohesion means a subsystem has a clear, focused role.

### One-line summary

Lecture 6 says: choose a simple high-level structure where subsystems have focused roles and minimal dependence on each other.

## Lecture 7

### Architecture Modeling and Styles

Lecture 7 makes architecture concrete: what parts exist, how to model them, and which recurring system structures are commonly used.

### Design vs architecture

| Type | Focus |
| --- | --- |
| Design | Local decisions inside parts of the system |
| Architecture | System-level structure and large-scale decisions |

### Architecture parts

| Part | Meaning |
| --- | --- |
| Package | Conceptual grouping of system elements |
| Component | Software unit with interfaces |
| Node | Physical place where software runs |

### Diagram types

| Diagram | Answers | Main unit |
| --- | --- | --- |
| Conceptual diagram | How are the main parts connected? | Packages |
| Interface / Component diagram | How are major parts connected logically? | Components |
| Deployment diagram | What runs where physically? | Nodes |

### Architectural styles

| Style | Core idea | Use when | Example |
| --- | --- | --- | --- |
| Client-Server | Clients and servers communicate through a protocol | Request/response across machines is natural | Email, internet services |
| Layered | Each layer uses the one below and serves the one above | You want clean abstraction boundaries and controlled dependencies | Operating systems |
| Pipe and Filter | Data moves through a sequence of transformations | The main job is step-by-step data transformation | Compiler, signal processing |
| Repository | Components coordinate through shared central data | The system revolves around shared state | Central database-based systems |

### Key intuitions

| Style | Intuition |
| --- | --- |
| Client-Server | One side asks, the other side serves |
| Layered | A stack where each layer mainly talks to its neighbors |
| Pipe and Filter | An assembly line for data |
| Repository | Everyone works through one shared source of truth |

### What to remember for the exam

- Packages show conceptual grouping.
- Components are software units with interfaces.
- Nodes are physical runtime resources.
- Use a deployment diagram when the question is about where software runs.
- Client-server is about protocol-based communication.
- Layered architecture is about abstraction boundaries.
- Pipe and filter is best for data transformation pipelines.
- Repository architecture centers the system around shared data.

### One-line summary

Lecture 7 says: model architecture through packages, components, and nodes, then choose a style like client-server, layered, pipe-and-filter, or repository to organize the system.

## Lecture 8

### Advanced Architecture Styles and Deployment

Lecture 8 continues architecture with event-driven styles and modern deployment approaches.

### Architectural styles continued

| Style | Core idea | Key point |
| --- | --- | --- |
| MVC | Split system into Model, View, Controller | Separates data, UI, and input/control logic |
| Publish-Subscribe | Publishers emit events, subscribers react | Event-driven and loosely coupled |

### Deployment and packaging styles

| Style | Core idea | Pros | Cons | Examples |
| --- | --- | --- | --- | --- |
| Virtualization | Multiple OS instances on one machine managed by a host OS/hypervisor | Lower cost, better hardware use | High overhead | VMware, VirtualBox, Xen |
| Containers | Lightweight package containing everything an app needs | Lighter than VMs, fast startup | Less isolation than full VMs | Docker, LXC |
| Serverless | Event-triggered functions run by a cloud platform | Less infra management, good for small triggered tasks | Harder to reason about distributed behavior | AWS Lambda, Azure Functions |
| Microservices | Many small independent services communicating over the network | Scalable, fault tolerant, reduces coupling | Coordination and operations become harder | Netflix, Amazon, Uber |

### Key intuitions

| Topic | Intuition |
| --- | --- |
| Publish-Subscribe | Components do not call each other directly; they react to events |
| Virtualization | Many virtual computers on one physical computer |
| Containers | Lightweight app packaging |
| Serverless | Small functions that run only when triggered |
| Microservices | Many mini-applications working together |

### What to remember for the exam

- Publish-subscribe is event-driven and loosely coupled.
- MVC separates data, UI, and control responsibilities.
- Virtual machines are heavier than containers.
- Containers package an application and its runtime needs.
- Serverless is good for small event-triggered functions.
- Microservices improve independence and scalability but increase operational complexity.

### One-line summary

Lecture 8 says: architecture also includes event flow and deployment strategy, from MVC and publish-subscribe to VMs, containers, serverless, and microservices.
