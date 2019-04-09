class: longlist
name: title
# SRE Book Report
### Blockchain Solutions Introspection
1. What is SRE?
2. Principles
3. Practices
4. Google's Suggestions for launching an SRE program
5. SRE engagement model
6. Key aspects of successful SRE programs

---
class: longlist
layout: false
.left-column[
## What is SRE?
]
.right-column[
1. SRE model compared to traditional operations
2. Responsibilities
3. What SRE is *not*
]

---
layout: false
.left-column[
## What is SRE?
The SRE approach compared to traditional operations.
]
.right-column[

### The SysAdmin Approach (a.k.a. traditional Ops)
- Composes existing software into deployments
- Runs service, respond to events and perform updates
  - The complexity and frequency of events that require an operator's manual intervention increase as the service scales
- **Operations team scales linearly to meet increased workload**
- Separated from product development

### The SRE Approach
- "when a software developer designs an operations team"
- 50% time spent on "ops work", with a hard cap.
- 50% time spent engineering.
  - This is **crucial**.  Without 50% of time spent on engineering, the ops load increases and you will need more people, sliding back into the traditional ops approach.
- Number of SREs **do not** scale with service load or size, only with service complexity.
- Embedded in product development teams.
  - Transfer between SRE and product development is easy.

]

---
name: sre-approach
layout: false
.left-column[
## What is SRE?
The SRE Approach
]
.right-column[
The SRE approach is focused on **repeatable processes**, **human interactions**, and **promoting good work habits** as a means to efficiently iterate on services while *avoiding previous errors* and minimizing *response time to new errors*.
]

--
template: sre-approach
.right-column[
The SRE approach is not:
- A backlog of specific tickets
- A product management checkbox to tick off
- A silver bullet or panacea
- Something that provides immediate results
- A place for product development to offload complexity
]

--
template: sre-approach
.right-column[
.blockquote[[...] are you interested in software development that produces results that can be used across teams, possibly as a standard for the organization? In larger established organizations, the latter change will take time, possibly spanning multiple years.]
.blockquote-source[Chapter 18 - Software Engineering in SRE]
]

---
layout: false
class: longlist
.left-column[
## What is SRE?
No immediate results?
]
.right-column[
### Our reliability is in the gutter and we need results now!

- You did not get here overnight.
- You won't be able to launch an SRE program overnight.
- You won't be able to increase your availability overnight.
  - Improving availability is a **time-gated** effort.
  - It must be supported by **long term strategies** that have impact on **day-to-day processes**.
- Your current situation is the result of a series of decisions, policies, and processes.
  - The SRE approach is concerned with providing concrete improvements (with sufficient explanations) on these policies and processes, driven by industry best practices and organizational data.
]

---
layout: false
class: longlist
.left-column[
## What is SRE?
Responsibilities
]
.right-column[
- Availability
- Latency
- Performance
- Efficiency
- Change management
- Monitoring
- Emergency response
- Capacity Planning
- Standards and best practices
]

---
class: longlist
layout: false
.left-column[
## SRE Core Principles
Concepts
]
.right-column[
These concepts are reused throughout this deck and the SRE book itself.

- **Operational load** (a.k.a ops load):
  - work that must be done to maintain the system in a functional state.
- **Toil** (a.k.a "kicking the can down the road") are tasks that are:
  - manual
  - repetitive
  - able to be automated
  - devoid of **enduring** value
- **Interrupts**:
  - are anything that force an SRE to switch context from their engineering work.
]

---
class: longlist
layout: false
.left-column[
## SRE Core Principles
Philosophies that drive SRE practices and engagement.
]
.right-column[
- Durable focus on engineering.
  - When ops load is > 50% of SRE bandwidth, product development needs to take excess tickets until balance is restored.
  - Aggressively automate toil.  Create software solutions for software problems.
- Large acceptance for change and rapid innovation.
- Release engineering.
  - Reduce release risk by releasing often.
- Policies enable software automation.
- Simplicity.
- Documentation and standardization make effort **permanent** and **portable**.
]

---
class: longlist
layout: false
.left-column[
## SRE Core Principles
Durable focus on engineering
]
.right-column[
## Why?
- SRE owned software projects ensure that highly qualified SWE will actually want to join your SRE organization.
- Operations load scaling can only be matched by automation.  This idea is the foundation that all of SRE is built on.
- Because SRE are embedded in the subject matter, they can understand the needs and requirements of the tool being developed.
- A direct relationship with users, fellow SREs and product developments, results in good user feedback, promoting quick launch and iteration cycles.
- Valuable SRE software projects typically start as side projects of a single SRE.
]

---
layout: false
.left-column[
## SRE Core Principles
Durable focus on engineering: **Toil**
]
.right-column[
## Toil?
**Toil** is any work that is
- manual
- repetitive
- able to be automated
- tactical
- **devoid of enduring value**
- scales linearly as organization grows or service traffic grows

The key aspect is that toil does not produce permanent value for your service.  When you toil, there is no progress, you are simply maintaining the status quo (and "kicking the can down the road").

.blockquote[If a human operator needs to touch your system during normal operations, you have a bug. The definition of normal changes as your systems grow.]
.blockquote-source[Carla Geisser, Google SRE]
]

---
class: longlist
layout: false
.left-column[
## SRE Core Principles
Durable focus on engineering: **Toil**
]
.right-column[
### Without a strict 50% time goal, toil will always rapidly expand to 100% of SRE time.

This is clear from Blockchain Solutions:
- At least one product is consumed by toil such that many individual work items aren't recorded in a tracking system.
- Operators in this situation are effectively fully committed to toil.
- Per the SRE model, this is the expected outcome of any service that does not carefully manage the time of their SRE.

This represents a type of **cascading failure**:
- If you are so busy performing toil that you cannot record the items in a work tracking system, then there is no way to measure the time spent toiling and address these issues.
]

---
class: longlist
layout: false
.left-column[
## SRE Core Principles
Durable focus on engineering: **What isn't toil**
]
.right-column[
- Writing or modifying code.
- Design and documentation.
- Configuration modification.
- Setup of services or managing software updates.
- Architecture consultation.
- Design meetings.
- Anything that produces **lasting** value for services and reliability.
]

---
class: longlist
layout: false
.left-column[
## SRE Core Principles
Durable focus on engineering: **Negative Impacts of Toil**
]
.right-column[
- Sets precedent for product development to load SREs with more toil.
  - If product development knows they can reliably offload tasks they don't want to perform, they are implicitly incentivized to do so.
- Creates confusion
  - Individuals or teams who toil too much muddy the water and create confusion about the role.
- Slows concrete progress.
  - Time spent toiling takes away from time spent on solutions that reduce the operational load of the service permanently.
- Breach of faith.
  - You want talented SWE to transfer to SRE.  To do this, you need to provide what you promised.
]

---
layout: false
.left-column[
## SRE Core Principles
Durable focus on engineering: **Interrupts**
]
.right-column[
Interrupts typically come in the form of:
- **Pages**: production alerts and associated work.
- **Tickets**: customer requests that require you to take an action, e.g.:
  - request to review configuration change
  - capacity planning
  - help with design
- Ongoing ops activities, a.k.a. **toiling**:
  - code or flag rollouts
  - responses to ad hoc / time sensitive questions

Each interrupt incurs a context switch.  Context switching is costly, each one piling up to take away hours from engaged engineering.  Managing these is a critical part of maintaining the 50/50 SRE time split.

.blockquote[Some interrupts are inevitable. However, viewing an engineer as an interruptible unit of work, whose context switches are free, is suboptimal [...]]
.blockquote-source[Chapter 29 - Dealing with Interrupts]
]

---
layout: false
.left-column[
## SRE Core Principles
Durable focus on engineering: **Dealing with interrupts**
]
.right-column[
SRE, like any engineer, benefit heavily from being able to get into a **flow state**.
]
--
.right-column[
Maximizing the amount of time a person can spend in this state is desirable -- they're going to produce creative results and do good work by volume.
]
--
.right-column[
Operators who are consistently interrupted to toil will be prevented from reaching this state, or may give up entirely.
]
--
.right-column[
Suggestions for dealing with interrupts:
- Stop randomly assigning tickets.  Make handling tickets a full time, rotational responsibility, called "on-interrupt".
- Define roles that let anyone on the team take up the mantle, so engineers aren't strapped with ongoing responsibilities.
- Analyze tickets for potential root causes.  Addressing these could significantly diminish or elminate a specific type of ticket.
]

---
layout: false
.left-column[
## SRE Core Principles
Durable focus on engineering: **Dealing with interrupts**
]
.right-column[
### Respect yourself, and your customers
Remember that it is OK to push some of the effort back onto your customers.
- If there are documented steps for an interrupt that are time-consuming or tricky, but can be done without your security privileges, consider using policy to push the request back to the requestor, e.g.:
  - Creating a deployment request
  - Changing a feature flag
  - Updating a monitoring dashboard or alert configuration

.blockquote[Your guiding principle in constructing a strategy for dealing with customer requests is that the request should be meaningful, be rational, and provide all the information and legwork you need in order to fulfill the request. In return, your response should be helpful and timely.]
.blockquote-source[Chapter 29 - Dealing with Interrupts]
]

---
layout: false
.left-column[
## SRE Core Principles
Release Engineering: **Philosophy**
]
.right-column[
### Self-service model
- Teams have to be able to manage, control, or otherwise run their own deployments, including to production.

### High Velocity
- Releases should be performed as frequently as possible.
- Frequent releases result in fewer changes per release.
- Fewer changes per release simplifies testing and troubleshooting when issues do arise with a release.

### Gated Actions
- Leverage gated actions to empower product development teams to self-serve

### Formal Process
- Without concrete release processes, you cannot automate, or add features to existing automation, in a responsible or effective way.
]

---
layout: false
.left-column[
## SRE Core Principles
Release Engineering: **Philosophy**
]
.right-column[
### Release Frequency Confirmation Bias
Blockchain solutions products deliberately release infrequently.
- At most, the formal release process recognizes one release per iteration.
  - Reality dictates that it happen more often than that, but the myth of the rare hotfix is another topic for another day.
- The reasoning behind this is typically that releases are risky.
  - However, the degree of risk for any given release is directly related to the number of changes in that release.
- Understanding that releases are risky leads to a self-fulfilling prophecy:
  - Avoiding frequent releases due to risk.
  - Not releasing frequently increases that risk by increasing the number of changes in each release.
  - An infrequent release fails or causes downtime, confirming bias against frequently releasing.
]

---
class: longlist
layout: false
.left-column[
## SRE Core Principles
Simplicity
]
.right-column[
.blockquote[Essential complexity is the complexity inherent in a given situation that cannot be removed from a problem definition, whereas accidental complexity is more fluid and can be resolved with engineering effort.]
.blockquote-source[Chapter 9 - Simplicity]

- SRE should get involved in reducing complexity in product source.
- When possible, actively limit scope of APIs.
- Modularity
  - Loosen coupling between binaries, or binaries and configuration
    - Promotes product development speed and stability
    - Rely on well defined versioning processes to allow product developers to use the version their system depends on while they upgrade to the newer version in a safe way.
]

---
layout: false
.left-column[
## Practices
Concrete practices promoted by SRE.
]
.right-column[
### Service Availability
- Figure out your error budget.
  - This **has** to be based on your SLA and SLO (service level objectives)
  - The book is clear: do not bother starting an SRE effort without an SLA or SLO in place.
- Measuring availability based on **time**:
  - `availability = uptime / (uptime + downtime)`
  - This is less meaningful for distributed systems.
  - You can be "up" somewhere in the world, but that doesn't necessarily tell you anything about your service's general availability.
- Measuring **aggregate** availability:
  - `availability = successful requests / total requests`
  - More generally useful for distributed systems.
  - Can also be used for non-serving systems with clear ideas of successful or unsuccessful units of work (batch processing, etc).
]

---
layout: false
.left-column[
## Practices
Concrete practices promoted by SRE.
]
.right-column[
### Service Availability
- Use percentiles over rates where possible:
  - `50 ms` average response time won't tell you if 5% of requests are taking `1000 ms`.
  - Try to avoid assuming your data has a normal distribution.
  - General rules of thumb:
    - 99th percentile -> worst case for your service
    - 50th percentile -> average case for your service
- Try to avoid assuming your data has a normal distribution.
  - Network timeouts and baseline cost for making a network request (e.g, no network request can be completed in `0 ms`) impact the distribution of your data.
- Standardize on common definitions to save time and confusion, e.g.:
  - aggregation intervals
  - how data is acquired
  - how frequently measurements are made
  - which requests are included
  - data-access latency
]

---
layout: false
.left-column[
## Practices
Concrete practices promoted by SRE.
]
.right-column[
### Monitoring
The amount of cycles spent on maintaining monitoring configurations for services inside Google dropped considerably after **centralizing** and **commonizing** the monitoring infrastructure.

This also serves another goal:
- Monitoring systems **need** to be kept simple and comprehensible by **everyone** on the team.
  - Avoid introducing new monitoring systems, if at all possible.
  - Each monitoring system has a "who guards the guards" problem, and each new system compounds this problem.
- Product developers unfamiliar with existing monitoring systems who are assigned work items related to service observability should consult with an SRE or have an SRE review their changes.
  - This is an example of how SRE can distribute and reinforce best practices in a deeper way than simply performing the work for product developers.
]

---
class: longlist
layout: false
.left-column[
## Practices
Concrete practices promoted by SRE.
]
.right-column[
### Release Engineering
- Define best practices for release and build tooling.
- Ensure releases are done in a consistent and repeatable way, automatically.
  - Progressive Rollouts
  - Quickly and accurately detect problems
  - Rollback
- Strive to make tools behave correctly by default and are sufficiently documented so teams can focus on feature delivery.
]

---
class: longlist
layout: false
.left-column[
## Practices
Concrete practices promoted by SRE.

**Continuous Build + Deploy**
]
.right-column[
### Release Engineering
#### Branching
- Don't release from `master`
  - Create a release branch
      - **Never** merge this back into `master`.
      - Merge any release fixes into `master` and cherry pick them onto the release branch.

#### Testing
- The CI build targets should be the same ones that gate releases of your service.
  - Unit tests
  - System tests
]

---
class: longlist
layout: false
.left-column[
## Practices
Concrete practices promoted by SRE.

**Continuous Build + Deploy**
]
.right-column[
### Release Engineering
#### Packaging
- Each package should be versioned with unique hash
- Use labels (`prod`, `dev`, `canary`, the build ID) to easily manage your packages.
- Results of each release step are logged.
- Report of all change since last release is created.
]

---
layout: false
.left-column[
## Practices
Concrete practices promoted by SRE.

**Continuous Build + Deploy**
]
.right-column[
### Release Engineering
#### Configuration Management
Some recommended strategies:
- Use `master` for configuration.
  - Allows for review of configuration
  - Applied on change as part of CI.
  - Service changes and configuration changes are decoupled.


- Include the configuration files in the service package.
  - Limits flexibility, but simplifies deployment.


- Package configuration into "configuration packages" using same standards as service release.
  - Can cherry pick configuration changes onto release branch without needing to rebuild service.
  - Ensures that all configuration changes don't have to be backwards compatible with all services.
]

---
layout: false
.left-column[
## Practices
Concrete practices promoted by SRE.
]
.right-column[
### Postmortems
- Vital to SRE model.
- Incidents and outages are inevitable given the scale and velocity of change.
- When an incident occurs, the issue is fixed, and services return to normal.
- Without a formalized process of learning from the incidents, they are likely to recur.
- Need to generate action items with deal with issues in a **permanent** way.

Define criteria for triggering postmortems before an incident occurs so that everyone knows when a postmortem is necessary:
- User-visible downtime or degradation beyond a certain threshold
- Data loss of any kind
- On-call engineer intervention
- A resolution time above threshold
- A monitoring failure (implies manual incident discovery)
]

---
class: longlist
layout: false
.left-column[
## Practices
Concrete practices promoted by SRE.
]
.right-column[
### Postmortems
.blockquote[For a postmortem to be truly blameless, it must focus on identifying the contributing causes of the incident without indicting any individual or team for bad or inappropriate behavior.]
.blockquote-source[Chapter 15 - Postmortem Culture: Learning from Failure]

- A focus on *why* an individual or a team had incomplete or incorrect information enables effective prevention plans.
- Postmortems are not a formality, they need to be seen by engineers as an opportunity to make the organization as a whole more resilient, beyond their service.
- Postmortem processes should highlight and lean on collaboration and knowledge-sharing.
]

---
layout: false
.left-column[
## Practices
Concrete practices promoted by SRE.
]
.right-column[
### Postmortems
- Use an in-house template: [Example Postmortem from SRE book](https://landing.google.com/sre/sre-book/chapters/postmortem)
- Your postmortem document tool of choice needs to support:
  - Real-time collaboration
  - Open commenting/annotation system
  - Email notifications
      - Ensures collaborators on the document receive feedback or loop others in for input.
- Some review items before finalizing a postmortem draft:
  - Was key incident data collected for posterity?
  - Are the impact assessments complete?
  - Was the root cause sufficiently deep?
  - Is the action plan appropriate and are action items at appropriate priority?
  - Did we share the outcome with relevant stakeholders?

The goal is to share the postmortem with the widest audience benefits from the knowledge or lessons imparted.  For BCS, this should be all of our product teams at a minimum.
]

---
layout: false
.left-column[
## Practices
Concrete practices promoted by SRE.
]
.right-column[
### Software Engineering
- Quality standards are the same as product development.
- An ad hoc approach does not scale as organizations grow in size and complexity, resulting in narrow software solutions that cannot be shared.
  - This results in duplicated efforts and wasted time, multiplying across the entire organization.
- Remain agnostic.  Do not create tools that
  - Are tightly coupled to your service details (they will change too, even if you don't intend on sharing the wealth)
  - Force users to commit to a single tool -- focus on remaining generic and composeable.

.blockquote[Reducing the number of ways to perform the same task allows the entire organization to benefit from the skills any single team has developed, thus making knowledge and effort portable across teams.]
.blockquote-source[Chapter 18 - Software Engineering in SRE]
]

---
layout: false
.left-column[
## Google's Suggestions for launching an SRE program
]
.right-column[
### Create and Communicate a Clear Message
- Your strategy and plans for this change need to be clearly defined in a publicly discoverable location, as well as actively pushed by organization leadership.  An organizational change of the scale is unlikely to succeed if the individuals enacting it do not all communicate the same important details.
- Highlight the benefits.

### Evaluate your organization's capabilities
- An SRE organization requires skills and roles that may not have been present in your traditional operations team, such as project manager.
- Identify and fill these gaps with skills already present.
  - Ask a product manager to help define product requirements and prioritize feature work
  - Lean on existing agile processes documented for product development.
]

---
layout: false
.left-column[
## Google's Suggestions for launching an SRE program
]
.right-column[
### Communication and Collaboration
- Inside Google, SRE is not a command-and-control organization
  - SRE have two masters
    - Work closely with a product development team
    - Report through SRE specific structure, providing independence
- It is vital that SREs are local to the service team.
- Hold production meetings
  - Weekly meeting where SRE team details the state of the service(s)
  - Meetings are **service-oriented**.  They are not about the status updates of individuals.
  - Goals:
      - Everyone leaves the meeting with the **same idea** of what's going on.
      - Improve the services by exposing operational details to wider audience
  - Discuss the operational performance of the service
    - Relate this to design, configuration, implementation, discuss recommended changes to address issues
    - Provides a powerful feedback loop
  - The meeting should have a rotating chair to reinforce shared ownership
]

---
layout: false
.left-column[
### Google's Suggestions for launching an SRE program

Approach for forming an SRE team in response to stability issues.
]
.right-column[
### Phase 1: Get Context
- Observe the product team's routine and practices.
- The goal is to identify which processes and habits are detracting from stability, not close as many tickets as possible.
- Avoid Ops Mode
  - "Ops Mode" occurs when teams increase toil as a service grows instead of pursuing scalable software solutions.
  - Teams sometimes fall into ops mode because they are focused on quickly addressing emergencies instead of how they can reduce the number of emergencies.
  - Almost always a result of overwhelming pressure.
- Identify Kindling
  - Knowledge gaps created by silos.  e.g., "`$eng` handles all monitoring/logging/database/networking items".
  - Postmortems only have action items for rolling back specific changes that caused the failure, instead of addressing root cause in a permanent way.
  - Capacity plan is "add more servers, we were running out of memory".  If you were running out of memory yesterday, and have no forecast, you have no idea whether or not you will run out of memory today, even with more compute resources.
]

---
layout: false
.left-column[
### Google's Suggestions for launching an SRE program

Approach for forming an SRE team in response to stability issues.
]
.right-column[
### Phase 2: Sharing Context
Lay the groundwork for improvement through best practices like postmortems and helping identify sources of toil and how to address them.

Write a good postmortem
- Postmortems offer insight into a team's collective reasoning.  Unhealthy teams rarely produce effective postmortems.
- The driver of the new SRE effort should take ownership of the next postmortem.
  - Team up with the on-call staff to write a blameless postmortem.
  - This document is an opportunity to demonstrate the value of the SRE model by making fixes more permanent.

Sort fires by type
- Sort the various fires into **toil** and **not-toil**.
- Present the list to the team and clearly explain why each fire is either work that should be automated or acceptable overhead for running the service.
]

---
layout: false
.left-column[
### Google's Suggestions for launching an SRE program

Approach for forming an SRE team in response to stability issues.
]
.right-column[
### Phase 3: Driving Change
Team health is a process.  It is not something you can solve with heroic effort.

.blockquote[Your first goal for the team should be writing a service level objective (SLO), if one doesn't already exist. The SLO is important because it provides a quantitative measure of the impact of outages, in addition to how important a process change could be. An SLO is probably the single most important lever for moving a team from reactive ops work to a healthy, long-term SRE focus. If this agreement is missing, no other advice in this chapter will be helpful. If you find yourself on a team without SLOs, first read Service Level Objectives, then get the tech leads and management in a room and start arbitrating.]
.blockquote-source[Chapter 30]
]

---
layout: false
.left-column[
### Google's Suggestions for launching an SRE program

Approach for forming an SRE team in response to stability issues.
]
.right-column[
### Phase 3: Driving Change
Get help clearing kindling
1. Find useful work that can be accomplished by one team member.
2. Clearly explain how this work addresses an issue from the postmortem in a **permanent** way.
3. Serve as the reviewer for the code changes and document revisions.
4. Repeat.

When you identify additional issues, put it in bug reports or documentation for the team to consult.
- Distributes information *and* encourages engineers to write docs.
- Emphasize that good docs ensure old mistakes don't get repeated.
]

---
layout: false
.left-column[
### Google's Suggestions for launching an SRE program

Approach for forming an SRE team in response to stability issues.
]
.right-column[
### Phase 3: Driving Change
Explain your reasoning
- As kindling is cleared, the day-to-day decision making that resulted in instability will need to be addressed.
  - This will be strongly challenged.
- Ensure that these changes are not seen as attacks by clearly explaining the reasoning behind them and providing specific ways that these changes prevent stability issues.
- The team should be able to predict what your comment on a design or code review would be.

Ask leading questions that encourage people to think about the basic principles.
- Be careful that these questions are not loaded or thinly veiled finger pointing.
]

---
layout: false
.left-column[
### Google's Suggestions for launching an SRE program

A real scenario with identifying details removed to avoid casting blame on the individuals involved.
]
.right-column[
**Scenario**: A product developer makes a change to a common library.  The scope of the change is a module related to core service infrastructure code (e.g., monitoring, logging, database clients, networking), without adding tests for the change.  Another product developer reviews the change, approves it, and merges it, because he and the other developer agree that the change cannot be captured in unit tests, and system tests aren't required for CI to pass for this common library.  Eventually, the code causes a production outage.

**Suggested Process Improvements** (that aren't likely to be popular):
- Someone from an SRE background would have been more likely to know how to test the change, and could have blocked merging the change until the developer delivered those tests.
- It may make sense for SRE to own that code outright, or be required to approve changes to the code.
- The CI build for any project should include system tests, especially if the CI build also gates release.
]


---
layout: false
.left-column[
## SRE engagement model
]
.right-column[
Google's initial SRE engagement model had some limitations:
- Service teams produced idiosyncratic services with high amounts of variation due to re-implementation of patterns.
  - These variations increase operational complexity and reduce efficiency.
- A review of common service outages revealed patterns, but replicated fixes or improvements across products was not straight-forward.
- SRE software contributions were often local to the service.
  - Building generic solutions at a reusable scale was difficult.
  - Difficult to share best practices.

To resolve these issues, Google transitioned to a structural solution: **Frameworks**
- Codified best practices
  - Ability to commit what works well to code, so services can be "production ready" out of the box.
- Reusable solutions
- Common production platform with a common control surface
  - Uniform interfaces, uniform monitoring, logging, and configuration for all services.
- Enable easier automation and smarter systems
]

---
layout: false
.left-column[
## SRE engagement model
]
.right-column[
SRE owned frameworks and platforms provided upfront gains in consistency and efficiency
- Freed developers to focus on business logic
- Consistent frameworks in multiple languages meant product teams can choose the language of their choice, while SREs and other on-call engineers can still expect familiar behavior of services in production
  - Standard instrumentation and monitoring data collection
  - Standard format for request debugging logs
  - Standard configuration formats
- Significantly lower operational overhead
  - Built-in deployment, monitoring, and automation
  - Easier to manage large numbers of micro-services due to operational consistency
  - Enables faster deployment, becoming production-ready in days.
- All services are automatically improved as common frameworks and modules are improved over time.
- Promotes a shared ownership model of service operation.
]

---
class: longlist
layout: false
.left-column[
## Key aspects of successful SRE programs

Summary
]
.right-column[
- Treated as an engineering organization
- Embedded locally with service teams
- Clear and concise communication
- Iterative
- Data driven
- Well defined role and responsibilities
- Establishing service level objectives (SLO)
- Easy to transfer between product development and SRE, or vise versa

<br>
<br>
.blockquote[Once an SRE team is in place, their potentially unorthodox approaches to service management require strong management support]
.blockquote-source[Chapter 1 - Introduction]
]

---
class: longlist
layout: false
.left-column[
## Key aspects of successful SRE programs

Summary
]
.right-column[
A protected 50/50 split between operations load and software engineering.

<br>
<br>
.blockquote[Google caps operational work for SREs at 50% of their time. Their remaining time should be spent using their coding skills on project work. In practice, this is accomplished by monitoring the amount of operational work being done by SREs, and redirecting excess operational work to the product development teams: reassigning bugs and tickets to development managers, [re]integrating developers into on-call pager rotations, and so on. The redirection ends when the operational load drops back to 50% or lower.]
.blockquote-source[Chapter 1 - Introduction]
]
