<h1 align="center">Midterm Review</h1>
<p align="center">Review and summary of course material covered by the midterm</p>

<h3 align="center">In class - February 26</h3>

<br><br>

| Format |
| ------ |
| <ul><li><b>80 minutes</b></li><li><b>Open book</b> - paper only (photocopy or hard copy of book).</li><li><b>Coverage:</b> All [lecture notes and listed readings](https://github.com/SENG480-18/course) up to February 5<sup>th</sup> inclusive</li><li><b>Four questions, choose one from each:</b></li><ul><li><b>Read code and interpret diagrams</b></li><li><b>Business cases</b> - "This is company X, these are their business goals" - produce QA and QAS's that demonstrate how the software meets the business goals.</li></ul></ul>|

| Hints |
|-------|
| <ul><li><b>Views</b>:</li><ul><li>Know the two Views we've covered.</li><li>Know what information a View provides.</li><li>Code will be in <b>Java or Python</b>.</li><li><b>No UML</b> or formal modelling language knowledge necessary, but may have to draw a diagram.</li><li>Know when (in which situation) to use a View.</li></ul><li><b>Architecture drivers</b></li><li><b>Quality attributes</b> and <b>QA Scenarios</b>.</li></ul> |
  
---

<br><br>
  

## Table of Contents
<sup>(in order of appearance)</sup>

### Lecture Notes
* [Introduction: What is Software Architecture?](#introduction-what-is-software-architecture)
* [Software Architecture Overview](#software-architecture-overview)
* [Reading Code](#reading-code)
* [Architecture Stakeholders and Requirements](#architecture-stakeholders-and-requirements)
* [Views on Architecture - Modules](#views-on-architecture---modules)
* [Views on Architecture - Component and Connector](#views-on-architecture---component-and-connector)
* [Architecture and Design](#architecture-and-design)
* [Documenting Behaviour](#documenting-behaviour)

### Readings
* [Textbook Chapter 1](#textbook-chapter-1)
* [Textbook Chapter 2](#textbook-chapter-2)
* [Textbook Chapter 3](#textbook-chapter-3)
* [Textbook Chapter 16](#textbook-chapter-16)
* [Textbook Chapter 18](#textbook-chapter-18)
* [Textbook Chapter 4](#textbook-chapter-4)
* [Textbook Chapter 17](#textbook-chapter-17)

### Other Resources
* [SEI View Example](#sei-view-example)
* [What is Architectural Design?](#what-is-architectural-design)
* [SEI Behaviour Tech Report](#sei-behaviour-tech-report)

---
  
<!-- Begin skeleton -->

### Textbook Chapter 1

<sup>(notes go here)</sup>


### Introduction: What is Software Architecture?
[Lecture 1](https://github.com/SENG480-18/course/blob/master/lectures/1-intro.md)

**Every system has an architecture.**

"The software architecture of a system is the set of structures needed to reason about the system, which comprise the software elements, relations among them, and properties of both.""

**Why do we care?**

We identify 7 main benefits of a clearly defined software architecture:

1. **Divide and conquer the problem** - Architecture shows us how to transition up and down the abstraction hierarchy (system purposes down to individual lines of code).
2. **Help manage tasks and facilitate collaboration** - The architecture helps us figure out who does what.
3. **A common language for the system** - We establish and reuse styles, patterns, and syntax (like UML)
4. **Force us to look beyond "function" and into qualities**.
5. **Connect business goals to actual software implementation**.
6. **Avoid high-cost mistakes** - by focusing on the "difficult" decisions.
7. **The best architectures create options** - The "Architectural Runway" consists of the existing code, components, and technical infrastructure needed to implement near-term features without excessive redesign and delay. It provides the necessary technical foundation for developing business initiatives and implementing new Features and/or Capabilities.

#### Why We Document

Software models are useful abstractions for reasoning about the system when the real world system is too complex to be easily reasoned with.

There are three main modes for creating a software model:

1. **Diagram as Sketch** - Sketches are usually only useful in a specific context.  Often, sketches alone will not contain enough information/context to accurately and meaningfully portray a system or some aspect thereof.  Sketches are typically short-term communication tools.

2. **Diagram as Blueprint** - Blueprints are built specifically to be **handed off** to downstream users (analogous with civil engineer handing off building blueprints to general contractor).  Blueprints are meant to be precise and unambiguous.

3. **Diagram as Executable** - This is most common where there are tight constraints on safety or security, such as in automotive software.  In this mode we may use a **code-generation** tool like [Simulink](https://www.mathworks.com/products/simulink.html) to draw block diagrams which a built-in compiler can then translate into **C** code.

>**Implications of documentation**
>
>* Systems have many (many) structures. We need to filter the ones we really care about.
>* No *single* structure is the architecture.
>* Every system has an architecture, which may be more or less visible in the docs.
>* We can only define whether an architecture (i.e. set of structures) is "good" or not by understanding how well it meets its quality requirements and ultimate business goals.

### Textbook Chapter 2

<sup>(notes go here)</sup>


### Software Architecture Overview
[Lecture 2](https://github.com/SENG480-18/course/blob/master/lectures/2-arch.md)

<sup>(notes go here)</sup>


### Textbook Chapter 3

**Enabling a System's QAs:**
* If your system requires high **performance**, then you need to pay attention to *managing the time-based behaviour of elements* (i.e. events), their use of shared resources, and the frequency and volume of inter-element communication.
* If you care about a system’s **availability**, you have to be concerned with how components take over for each other in the event of a failure, and *how the system responds to a fault*.
* If you care about **usability**, you have to be concerned about isolating the details of the user interface and those elements responsible for the *user experience* from the rest of the system, so that those things can be tailored and improved over time.
* If you care about the **testability** of your system, you have to be concerned about the testability of individual elements, which means making their state *observable and controllable*, plus understanding the emergent behaviour of the elements working together.
* If **modifability** is important, then you need to pay careful attention to assigning responsibilities to elements so that the majority of changes to the system will affect a small number of those elements. (Ideally each change will affect just a single element.)
* If your system must be **highly secure**, then you need to manage and protect inter-element communication and control which elements are allowed to access which information; you may also need to introduce specialized elements (such as an authorization mechanism) into the architecture.
* If you want the elements from your system to be **reusable** in other systems, then you need to restrict inter-element coupling, so that when you extract an element, it does not come out with too many attachments to its current environment to be useful.


### Reading Code
[Lecture 3](https://github.com/SENG480-18/course/blob/master/lectures/3-reading.md)

<sup>(notes go here)</sup>


### Textbook Chapter 16

* An **ASR** will have a profound effect on the architecture - the architecture would be different in the absence of such a requirement - requirements that affect the making of critical arch. design decisions.
* Choosing ASRs to produce the architecture that will respond to the projects needs.
* **Quality Attribute** requirements, if important, should be specified unabmibuously and testable.
* ASRs often derive from business goals in the development organization itself - have high business or mission value
* **Business goals** are the reason for building a system i.e. make a profit - they are the precursor of requirements whose achievement signals a successful architectural design -- lead to ASRs
![business goals -> QA -> Architecture](/ch16image.png "Textbook Ch 16.3")

### Architecture Stakeholders and Requirements
[Lecture 4](https://github.com/SENG480-18/course/blob/master/lectures/4-req.md)

#### Stakeholders Roles & Concerns:
* Acquirers	Oversee the procurement of the system or product
* Assessors	Oversee the system’s conformance to standards and legal regulation
* Communicators	Explain the system to other stakeholders via its documentation and training materials	
* Developers	Construct and deploy the system from specifications (or lead the teams that do this)
* Maintainers	Manage the evolution of the system once it is operational	
* Production Engineers	Design, deploy, and manage the hardware and software environments in which the system will be built, tested, and run
* Suppliers	Build and/or supply the hardware, software, or infrastructure on which the system will run
* Support Staff	Provide support to users for the product or system when it is running
* System	Administrators	Run the system once it has been deployed	
* Testers	Test the system to ensure that it is suitable for use	
* Users	Define the system’s functionality and ultimately make use of it	

Each stakeholder cares more/less about different aspects of the system, not every stakeholder's opinion has equal weight.

#### Architecturally Significant Requirements
In order to find the ASRs, you should think about what an architect would do in a "rational design process":
* Requirements define expected behavior, ideally in concrete (yes/no) terms.
* Architecture provides an analysis model to predict behavior of the eventual system
* Properties (e.g. via testing) show actual behavior, which we analyse to determine satisfaction of the requirements.

ASRs are hard/unlikely to change and have wide impact on the system. Quality Attributes are the reqiurements that are important in architectural setting (how well the system works i.e. performance & the "ilities") ande help us understand the ASRs.

**Scenarios** have these parts :

| Aspect | Details |
|--------|---------|
|Scenario Name | |
|Business Goals | the impacted business goals |
| Quality Attributes | the key QA involved in this scenario | 
| Stimulus | a condition that affects the system |
| Stimulus Source | an entity that generates a stimulus | 
| Response | the activity that results because of the stimulus |
| Response Measure | the measure by which the system’s response will be evaluated |
* does the proposed measure meet the QA and satisfy the business goals?
* An architecture driver is a key decision that will influence what the system can and cannot do

### Textbook Chapter 18

* A **view** is a representation of a set of system elements and relations among them — not all system elements, but those of a particular type.
* What are the relevant views? This depends entirely on your goals. 
* Different views expose different quality attributes to different degrees.
* Views may be driven by the need to document a particular pattern in your design. Some patterns are composed of **modules**, others of **components and connectors**, and still others have deployment considerations.
* Example module views are *decomposition, uses,* and *layers*.

#### Module View
* A **module** is an implementation unit that provides a coherent set of responsibilities. A module might take the form of a class, a collection of classes, a layer, an aspect, or any decomposition of the implementation unit.
* Module views that show dependencies among modules or layers provide a good basis for change-impact analysis. 
* A module view can be used to explain the system’s functionality to some- one not familiar with it. 
![Summary of the Module Views](/ch18ModuleViewsSummary.png "Textbook Ch 18.1")

### C&C View
* Component-and-connector views show elements that have some runtime pres- ence, such as processes, objects, clients, servers, and data stores. These elements are termed **components**. Additionally, component-and-connector views include as elements the pathways of interaction, such as communication links and proto- cols, information  ows, and access to shared storage. Such interactions are represented as **connectors** in C&C views. 
* Sample C&C views are service-oriented architecture (SOA), client-server, or communicating process views.
* Components have interfaces called *ports*. A port defines a point of potential interaction of a component with its environment.
* Connectors often represent much more complex forms of interaction. Connectors have *roles*, which are its interfaces, de ning the ways in which the connector may be used by components to carry out interaction. 
* The primary relation within a C&C view is *attachment*. *Attachments* indicate which connectors are attached to which components, thereby de ning a system as a graph of components and connectors.
* An element (component or connector) of a C&C view will have various associated *properties* such as reliability, performance, resource requirements, functionality, security, concurrency, modifiability, tier.
* C&C views are commonly used to show to developers and other stakehold- ers how the system works—one can “animate” or trace through a C&C view, showing an end-to-end thread of activity.
* C&C views are also used to reason about runtime system quality attributes, such as performance and availability. 
![Summary of the C&C Views](/Ch18CCViewsSummary.png "Textbook Ch 18.2")

### Views on Architecture - Modules
[Lecture 5](https://github.com/SENG480-18/course/blob/master/lectures/5-modules.md)

**Structure:** a set of components, relationships, and properties of both. Constraints on what can be in a given structure - what is allowed and not allowed defines what type of reasoning we can conduct.

Think about a structure as **view on a particular system**. The views can be defined to show different information - what we want to show will be informed by what we care about. Typically, this is to answer questions like:
* what is going on when the system is running?
* how do we organize the code to work on it?
* what pieces need building first?
* how does it handle my requirements?
* what parts are from other vendors?
* how do I deploy this?
* what types of hardware demands does the system have?
* how does it manage security?
* how fast is it running?

A **view** reflects a particular structure of interest; a view may be composed of different styles. Each **style** imposes constraints on the view topology (e.g. no circular relationships) and relevant properties (always name, but perhaps strength of relationship, responsibilities, etc.)

#### Module View 
Elements: modules, implementation units of software with a coherent set of responsibilities. Relations: typically part of, depends on, is-a Usage: change impact analysis, incremental development, work assignment, information structures
* Instances of Module View styles: Layers, Uses, Generalization, Data Models, and others

An architectural style is an encapsulation of a solution to a problem.

**Layers Style** Show the permitted relationships between modules. A common overview for showing system context.

*Elements: *layers Relations: "allowed to use" (A uses B if A depends on B's correct functioning) *Constraints:* software in exactly one layer; software can only use software in a(ny) lower layer

**Uses Style** Tells the developer what other modules must exist for this portion of the system to work correctly. ie. Planning incremental development, Debugging and testing, Change impact analysis

*Elements:* modules *Relations:* "uses" *Constraints:* None.

**Generalization Style** The classic object model or class diagram notation. Captures commonalities, reuse opportunities, system organization. Describe data structures, communicate with possibly separate DBA team, help with domain analysis, help with module implementation.

*Elements:* modules *Relations:* 'is-a' *Constraints:* number of parents, no cycles

**Data Model Style** Models important data entities and the relations among them. Classic SENG370 or SQL ER diagrams are data model styles.

*Elements:* Data entity representing data to be stored in system. *Relations:* 1:1, 1:*, etc. *Constraints:* normalization


### Textbook Chapter 4

All requirements encompass the following categories:
1. Functional requirements.
2. **Quality attribute** requirements.
3. Constraints. 

What is the “response” of architecture to each of these kinds of requirements?
1. *Functional* requirements are satisfied by assigning an appropriate sequence of responsibilities throughout the design. Assigning responsibilities to architectural elements is a fundamental architectural design decision.
2. *Quality attribute* requirements are satisfied by the various structures designed into the architecture, and the behaviors and interactions of the elements that populate those structures.
3. *Constraints* are satisfied by accepting the design decision and reconciling it with other affected design decisions.

To summarize how we specify quality attribute requirements, we capture them formally as four-part **scenarios**. 
1. *Source of stimulus.* This is some entity (a human, a computer system, or any other actuator) that generated the stimulus.
2. *Stimulus.* The stimulus is a condition that requires a response when it ar- rives at a system.
3. *Response.* The response is the activity undertaken as the result of the arrival of the stimulus.
4. *Response measure.* When the response occurs, it should be measurable in some fashion so that the requirement can be tested.

### [SEI View Example](https://wiki.sei.cmu.edu/sad/index.php/OPC_Module_Uses_View)

<sup>(notes go here)</sup>


### Views on Architecture - Component and Connector
[Lecture 6](https://github.com/SENG480-18/course/blob/master/lectures/6-cc.md)

We should capture how these elements connect to one another; at its most basic this is an API specification (method name, parameters, return values, semantics). We also need to capture the ways these elements behave at runtime.

#### C&C View
*Elements:* components: principal units of runtime interaction and data stores and connectors: interaction mechanisms *Relations:* attachment of components’ ports to connectors’ roles (interfaces with protocols) *Properties:* name, relevant QA

Questions C&C views can answer: Specifying the behaviour that elements must exhibit; Show how the system "works"; Reasoning about runtime system quality attributes such as performance, security, and reliability; What are the major executing components?; Which parts of the system are replicated?; Data Flows; Which parts of the system can run in parallel?
* Instances of C&C Views styles: Pipe and Filter, Client-Server, Shared Data, Pub-Sub, Service Oriented

**Pipe and Filter** Show dataflow. Filters transform data and pass it along Pipes. Analyze system throughput, function composition.

*Elements*: Filters, data transducers as components. Pipes as one way data conduits.
*Relations*: ports connecting pipes and filters.
*Constraints*: restrict loops and branches.

**Client-Server** Shows modifiability and reuse possible in a 2 tier architecture. Analyze availability, connections expected, requests, interface needs.

*Elements*: Client invokes services from Server. Request/reply connector joins them.
*Relations*: attach client to server
*Constraints*: number of tiers; how connections are made;

**Shared Data** Read and write to a shared data store. Analyze data needs, identify who connects.

*Elements*: data stores and accessors.
*Relations*: attachments.
*Constraints*: how the data is attached via connectors.

**Pub-Sub** Decouple listeners from publishers. A very common pattern (e.g. Observer), it essentially wraps up asynchronous/callback architectures. Helps isolate consumers and producers, analyze decoupling and independence in your architecture.

*Elements*: publisher and subscribers. Possibly the bus for distributing messages
*Relations*: attachments.
*Constraints*: who can listen, message semantics.


### Textbook Chapter 17

<sup>(notes go here)</sup>


### [What is Architectural Design?](http://www.informit.com/articles/article.aspx?p=2738304&seqNum=2)

<sup>(notes go here)</sup>


### Architecture and Design
[Lecture 7](https://github.com/SENG480-18/course/blob/master/lectures/7-design.md)

<sup>(notes go here)</sup>


### [SEI Behaviour Tech Report](http://repository.cmu.edu/cgi/viewcontent.cgi?article=1680&context=compsci)

<sup>(notes go here)</sup>


### Documenting Behaviour
[Lecture 8](https://github.com/SENG480-18/course/blob/master/lectures/8-behavior.md)

<sup>(notes go here)</sup>

<!-- End skeleton -->
