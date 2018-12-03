# COMP3111 Revision Notes

## Introduction

### Complexities of Software

#### Source of complexities

- Application domain
  - Complex problems
  - Developers without domain-specific background
- Communication between stakeholders
  - Stakeholders uses different vocabulary
  - Stakeholders have different background knowledge
  - Ambiguous use of language
- Management of large software development projects
  - Need to "Divide and Conquer" the project
  - Need to coordinate different parts and people
- Coding
  - Creating software is inheritly complicated

#### Consequences of complexities

- Quality issues
  - Unreliabe software
  - Unsafe application developed
  - Abandonment of project
  - Inflexible project management
- Development Problems
  - Over schedule and over budget
  - Does not meet user requirements
  - Slow progress
  - Difficult to measure progress

#### Dealing with complexities

- Many desirable software quality characteristics
  - Impossible to achieve all characteristics simultaneously
- Need to clearly understand design goals
- Need to prioritize design goals for a project
- **Aim: Reduce the complexity of designing the system**

#### Modular & Incremental Development

- Issue: Limit to Human Understanding
- Solution: Divide (into modules) and Conquer
- Module: Part of system that makes sense to consider separately
  - Problem: Inter-module interactions
  - Solution: See below
- Interfaces: Implementation of information hiding
  - Achieves abstraction
    - Module can be used without understanding the implementation
    - **Reduces complexity of understanding the system**
  - Achieves encapsulation
    - Module can be changed without affect the module behavior
    - **Reduces complexity of maintaining the system**
- Result of using Modular & Increment Development
  - More productivity in team development
  - Fewer bugs in system development
  - More maintainable software
  - More reusable software
  - More predictable software development

#### Training Software Engineers

- Definition: **"programming-in-the-small" = coding**
- Definition: **"programming-in-the-large" = software engineering**
- Abilities of a software engineer:
  - *Talk to users* in terms of the application
  - *Translate vague requirements* into specifications
  - *Build models of a system* at different levels of abstraction
  - *Use and apply* several software development processes
  - *Choose among design alternatives* (e.g. make design tradeoffs)
  - *Work in well-defined roles* as a part of a team
- **Reduces the complexity of building the system**

## Modeling Software Systems using UML

### Table of Contents

- UML and Object-Oriented Modeling
  - [Overview of UML](#what-is-uml-)
  - [Object-Oriented Modeling](#why-object-oriented-modeling-)
- [Class](#class)
  - [Attribute](#class-attribute)
  - [Operation](#class-operation)
- [Association](#association)
  - [Multiplicity](#association--multiplicity)
  - [Aggregation and Composition](#aggregation-composition-association)
- [Association Class](#association-class)
- [Generalization](#generalization)
  - [Inheritance](#generalization--winter)
  - [Coverage](#generalization--coverage)
- [Constraints](#constraints)

### What is UML?

- General-purpose visual modeling language for systems
- Incorporates current best practices in OO modeling techniques
- Software development methodology/process neutral
- Industry-standard OO modeling language for modeling systems

#### Why Build Models?

- Models abstract reality
  - Shows essential details and filters everything else
- Allows us to focus on programming-in-the-large
- Allows to better deal with *complexity* of software development
- Results in better understanding of requirements, cleaner designs, and more maintainable systems

### Why Object-Oriented Modeling?

- Allows direct representation of "things" in application domain
  - Reduces "semantic gap" between application domain and model
  - Better represents reality as perceived by people
- **Applicaiton Domain is modeled as a collection of objects.**

#### OO Modeling & Levels of Abstraction

- Requirements Level: Constructed by Requirements Model
  - Do not consider implementation
  - **Focus: Identifying objects/concepts in the application domain**
- Analysis & Design Level: Constructed by Solution Model
  - Consider interfaces of objects
  - **Focus: How objects interact in the solution**
- Implementation Level: Implements Solution Model
  - Consider all details of objects
  - **Focus: How to code objects**

### Class

```
---------------------
|      Account      |  <- Class Name
---------------------
| account#: Int     |  <- Attribute Compartment
| amount: Money     |
---------------------
| balance(): Money  |  <- Operation Compartment
| deposit(amount)   |
| withdraw(amount)  |
| payInterest()     |
---------------------
```

- Describes a **collection of objects** with common:
  - Sematics
  - Attributes
  - Operations
  - Relationships
- Factory for creating objects
- Should capture only one abstraction
- Named using vocabulary of the application domain
  - Meaningful and Traceable from the application domain to model

#### Class Attribute

- Describes the **data values** held by obejcts in a class.
- Syntax: `[ visibility ] < property-name > [ : property-type ] [ [multiplicity] ] [ = default-value ] [ property-modifier ]`
  - `visibility`: Who can access the attribute's values
    - `+`: `public`
    - `-`: `private`
    - `#`: `protected`
    - `~`: `package`
  - `property-name`: Unique within a class
  - `property-type`: Domain of values (e.g. string, integer, money etc.)
  - `multiplicity`: Number of simutaneous values
  - `default-value`: Attribute's initial value
  - `property-modifiers`: Unspecified or `readOnly`

#### Class Operation

- Describes a **function** or **transformation** that may be **applied to or by objects** in a class.
- Syntax: `[ visibility ] < signature >`
  - `visibility`: Who can access the attribute's values
    - `+`: `public`
    - `-`: `private`
    - `#`: `protected`
    - `~`: `package`
  - `signature`: `< operation-name > < ( parameter-list ) > < : return-spec >`
- Implementation of operation = Method
  - Operation can ahve several methods that implement it (*polymorphic operation*)

### Association

![Association Diagram](img/02-association.png)

- Describes a **collection of links** with **common semantics**
  - Association is a classifier
  - Link is an instance
- Inherently *bi-directional*
- Can show navigability using arrowhead (`->`)
  - Implies source object has reference to target object

#### Association and Classes

- Two different classes be related by several associations
![](img/02-association-multiple-class.png)

- Same class can be related by several associations
![](img/02-association-single-class.png)

#### Association: Degree

- Unary: Relates one class to itself
  - `Person Manages Person`
- Binary: Relates two classes
  - `Customer Holds Account`

#### Association: Multiplicity

- Specifies a **restriction** on the **number of objects in a class** that may be **related to** an **object in another
class**.
- Example: `Bank[1..1] IsWith Account[0..*]`
  - A bank may have `0..*` accounts
  - An account must be with `1..1` bank
- Cardinality (`a..b`)
  - `a`: Minimum Cardinality
    - Minimum number of links
    - `a = 0`: Optional Participation
    - `a > 0`: Mandatory Participation
  - `b`: Maximum Cardinality
    - Maximum number of links
  - Special Cardinalities
    - `1` implies `1..1`
    - `*` implies `0..*`

#### Association: Role

- One end of an association
- Necessary to use role names when association *relates object from the same class*
  - Disambiguates relationships

![](img/02-association-role.png)

#### Aggregation/Composition Association

- Describes assocations between classes which are "part-of" one-another
- Aggregation: Component may exist independently of the aggregate object

![](img/02-association-aggregation.png)

- Composition: Component may **not** exist independently of the aggregate object

![](img/02-association-composition.png)

- When to use Aggregation/Composition?
  - Aggregation *iff* class is **intrinsically** "part of" another class
  - Composition *iff* class operations can be applied to another class
  - If in doubt, just use *association*

### Association Class

![Association Class](img/03-association-class.png)

- Usually used for many-to-many associations

### Generalization

- **Relationship** between **classes** of the **same kind**
- Classified by similarities of:
  - Attributes
  - Operations
  - Associations
- Goal: **Simplicity** of representation and **clarity** of modeling

![](img/03-generalization.png)

#### Generalization: Inheritance

- **Taking up of properties** by a subclass from its superclass
- Associate common "things" to superclass, inherit them to subclass(es)
- Benefits:
  - Reduces redundency
  - Promotes reusability
  - Simplifies modification
- Subclass may:
  - Add new properties
  - Override superclass methods

#### Generalization: Abstract Class

- Class that has **no direct instances**
- Container for definitions

![](img/03-generalization-abstract-class.png)

#### Generalization: Coverage

- Disjointness Coverage
  - `{overlapping}`: A superclass object can be a member of more than one subclass

![](img/03-generalization-overlapping.png)

  - `{disjoint}`: A superclass object is a member of at most one subclass

![](img/03-generalization-disjoint.png)

- Completeness Coverage
  - `{complete}`: All superclass objects must be instances of some subclass

![](img/03-generalization-complete.png)

  - `{incomplete}`: Some superclass object is not a member of any subclass

![](img/03-generalization-incomplete.png)

Example of all coverage types:

![](img/03-generalization-example.png)

### Constraints

- **Assertion about properties** of model elements that **must be satisfied** by the system
- Should be enforced by the system implementation

![](img/03-constraints.png)

- Types of Constraints
  - `{ordering}`
  - `{subset}`: Describes generalization of associations
  - `{xor}`: Only one of the associations can be active at once

![](img/03-constraints-example.png)

## Software Engineering

- Software Development Life-Cycle Stages
  - Definition
  - Design
  - Development
  - Operation

### Four P's in Software Development

#### Project

- Compose a project plan, which includes:
  - Scope, objectives, constraints
    - Define the problem and set design goals
    - Analyze the requirements
    - Prepare a top-level system diagram
    - Estimate the time and effort
  - Risks
    - Murphy's Law
    - Identify likelihood and impact of risk + Confidence of risk assessment
    - Use 80:20 rule for estimation
  - Organization
    - Specify roles and responsibilities
    - Assign clear responsibilities with PICs for each team
  - Tasks and activities
    - **Task: Well-defined work assignment for a role**
    - **Activity: Group of related tasks**
    - Plan-Driven vs Agile-Driven development
  - Schedule
    - Specifies task ordering, time ordering, resource assignment, milestones, deliverables
    - **Master Schedule: Project Management**
    - **Macro Schedule: Day-to-Day Project Management**
    - **Micro Schedule: Team Management**
  - Estimations

#### Process

- Prescribes all major activities
- Has a set of guiding principles
- Uses resources to produce intermediate and final products
- May be composed of subprocesses
- Has an entry and exit criteria
- Organized in a sequence
- Constraints or controls may apply

#### (The other two P's)

- People
- Product

### Waterfall Process

![](img/05-waterfall.png)

| Pros | Cons |
| ---- | ---- |
| Imposes needed discipline | Assumes linear, sequential development is possible |
| Keeps development predictable and easy to monitor | Phases can be frozen until results are rigid |
| Enforces documentation standards and approval of documents | Different languages often used in each phase |
| Fits well with other engineering process models | Makes little opportunity for user feedback |

### Code-and-Fix Process

![](img/05-code-and-fix.png)

- Many changes
  - Leads to messy code structure
- Unsuitable for large systems
  - Turnover of personnel
  - Difficult to understand/fix code
  - Mismatching requirements

### Prototyping Process

![](img/05-prototyping.png)

- Code-and-Fix + Client Evaluation + Self-discipline
- Useful when requirements are vague or unknown

| Pros | Cons |
| ---- | ---- |
| Allows exploration of requirements | Not a complete software development process |
| Allows user feedback and approval | Process is not visible |
| Allows different solutions to be explored | Documentation is often sparse or absent |
| <p> | Final product is not a complete system |

### Spiral Process

![](img/05-spiral.png)

| Pros | Cons |
| ---- | ---- |
| Risk evaluation can elp reduce development problems | Relies on expertise in risk assessment |
| Planning/Evaluation phases help meet client expectations | Needs more elaboration of phases |
| Iterative and incremental workflow facilities project management | More appropriate for internal development |

### Phased-Release Process

![](img/05-phased-release.png)

- Plan for changes ahead-of-time
  - Incremental Development: Parital system with full functionality
  - Iterative Development: Full system with partial functionality

| Pros | Cons |
| ---- | ---- |
| Reduces risk of project failure | Components need to be small |
| Promotes system modularity | Hard to identify common facilities required by all modules |
| Allows frequent releases | |
| Allows appropriate expertise to be applied |
| Allows early training and feedback | |

### Agile Process

- Any increment approaches where emphasis is placed on:

| More Important | Less Important |
| -------------- | -------------- |
| Individuals and Interactions | Processes and Tools |
| Working Software | Comprehensive Documentation |
| Client involvement/collaboration | Contract negotiation |
| Responsiveness to Change | Following a plan |

- Methods
  - Extreme Programming
  - Scrum

| Pros | Cons |
| ---- | ---- |
| Development is adaptable to changing requrements | Active user involvement and close collaboration required |
| Immediate feedback is provided | Lack of documentation |
| Faster speed-to-market | Potential scope-creep (adding of requirements) |
| Fewer defects in final product | Daily meetings can take a toll |

#### Extreme Programming

- Iterative programming, where each iteration:
  - Client selects features to be included
  - Developer breaks each iteration into tasks
  - For each task:
    - Designs task cases
    - Implements task using pair programming
    - Integrates the task into the product

#### Scrum

- No specific engineering practices: Team decide how to achieve tasks
- Requirements captured as items in a "product backlog"
- Developed in (iterative) "sprints"
  - Requirements not allowed to change during a sprint
