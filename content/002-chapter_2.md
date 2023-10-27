# Requirement Engineering and System Modeling
### Methodology
The Systems Development Life Cycle (SDLC) provides the foundation for
the processes used to develop an information system. A methodology is a
formalized approach to implementing the SDLC (i.e., it is a list of steps and
deliverables). There are many different systems development methodologies,
and they vary in terms of the progression that is followed through the phases
of the SDLC. Some methodologies are formal standards used by government
agencies, while others have been developed by consulting firms to sell to
clients. Many organizations have their own internal methodologies that have
been refined over the years, and they explain exactly how each phase of the
SDLC is to be performed in that company. Here we will review methodology
that have used in Kabul University Central Library Management information
system that is Agile development methodology that focus on the streamlining
the SDLC it is iterative application development in which every iteration is a
complete software project, including planning, requirements analysis, design,
coding, testing, and documentation. There are several popular approaches
to agile development methodology but we have used the scrum method that
has three roles product owner, scrum master and team so this approach is
fit and compatible with our requirement and organization structure.

### Agile Methodology
There are various methodologies that are collectively known as agile, as they
promote the values of the agile manifesto and they are consistent with the
above principles. The most popular ones are: DSDM :is probably the orig-
inal agile development method. DSDM was around before the term agile
was even invented, but is absolutely based on all the principles weve come
to know as agile. DSDM seems to be much less well-known outside of the
UK. XP :(Extreme Programming) is a more radical agile methodology, fo-
cusing more on the software engineering process and addressing the analysis,
development and test phases with novel approaches that make a substantial
difference to the quality of the end product. DSDM :is probably the most
complete agile methodology, whereas Scrum and XP are easier to implement
and complementary because they tackle different aspects of software devel-
opment projects and are both founded on very similar concepts. SCRUM :
Scrum is a subset of Agile. It is a lightweight process framework for agile
development, and the most widely-used one. a) A process framework is a
particular set of practices that must be followed in order for a process to be
consistent with the framework. (For example, the Scrum process framework
requires the use of development cycles called Sprints, the XP framework
requires pair programming, and so forth.) b) Lightweight means that the
overhead of the process is kept as small as possible, to maximize the amount
of productive time available for getting useful work done. A Scrum process
is distinguished from other agile processes by specific concepts and practices,
divided into the three categories of Roles, Artifacts, and Time Boxes. These
and other terms used in Scrum are defined below. Scrum is most often used
to manage complex software and product development, using iterative and
incremental practices. Scrum significantly increases productivity and reduces
time to benefits relative to classic waterfall processes. I. Increase the qual-
ity of the deliverables II. Provide better estimates while spending less time
creating them III. Be more in control of the project schedule and state. The
catalog Books form.


### Requirement Engineering
The requirements for a system are the descriptions of what the system should
do the services that it provides and the constraints on its operation. These
requirements reflect the needs of customers for a system that serves a certain
purpose such as controlling a device, placing an order, or finding information.
The process of finding out, analyzing, documenting and checking these ser-
vices and constraints is called requirements engineering (RE). a requirement
is simply a high-level, abstract statement of a service that a system should
provide or a constraint on a system. System modeling is the process of de-
veloping abstract models of a system, with each model presenting a different
view or perspective of that system. System modeling has generally come to
mean representing the system using some kind of graphical notation, which
is now almost always based on notations in the Unified Modeling Language
(UML). However, it is also possible to develop formal (mathematical) models
of a system, usually as a detailed system specification.

### Requirement Engineering of our Project
The web application we have designed is intended for companies and groups involved in application development. To meet user expectations, system developers must have a comprehensive understanding of the organization's operations. The primary objective of gathering information is to identify the information needs of the organization. While various methods exist for collecting organizational requirements, this project has employed highly efficient methods. These methods include:
User Interviews: Engaging with key stakeholders and potential end-users to directly gather their input on the application's requirements.
Surveys and Questionnaires: Collecting structured feedback from a broader audience to ensure a comprehensive understanding of user needs.
Observation: Studying the organization's working processes and interactions to identify underlying requirements and challenges.
Prototyping: Creating preliminary application models to visualize and refine user expectations and functionality.
Collaborative Workshops: Organizing workshops and brainstorming sessions with developers and users to foster collaboration and refine requirements.

### Functional and Non-Functional Requirement
Software system requirements are often classified as functional requirements
or nonfunctional requirements:

### Functional Requirement
The functional requirements for a system describe what the system should
do. These requirements depend on the type of software being developed, the
expected users of the software, and the general approach taken by the orga-
nization when writing requirements. When expressed as user requirements,
functional requirements are usually described in an abstract way that can
be understood by system users. However, more specific functional system
requirements describe the system functions, its inputs and outputs, excep-
tions, etc., in detail. Functional system requirements vary from general re-
quirements covering what the system should do to very specific requirements
reflecting local ways of working or an organizations existing systems.

### Functional Requirement of Our Project
In Software engineering and systems engineering, a functional requirement
defines a function of a system or its component. A function is described as
a set of inputs, the behavior, and outputs. Functional requirements may be
calculations, technical details, data manipulation and processing and other
specific functionality that define what a system is supposed to accomplish.
Player Can create account in the system. User can create project and manage
projects that belongs to him/her. Project manager can create user stories
of the specific project. Project manager create the user stories. Player vote
for the each user story. The system calculate the average of the story point
which belong to the each user story.

### Non-functional Requirements of our project
Non-functional requirements of this system cover all the remaining require-
ments which are not covered by the functional requirements[4]. They specify
criteria that judge the operation of this system, rather than specific be-
haviours, like: When user logged in, if again users accessing his/her account
don’t need to login again. Non-functional requirements are: Performance
Scalability Capacity Availability Reliability Maintainability Manageability
Usability Interoperability As said above, non-functional requirements spec-
ify the systems quality characteristics or quality attributes.

### System Modeling
System modeling is the process of developing abstract models of a system,
with each model presenting a different view or perspective of that system.
System modeling has generally come to mean representing the system using
some kind of graphical notation, which is now almost always based on nota-
tions in the Unified Modeling Language (UML). However, it is also possible
to develop formal (mathematical) models of a system, usually as a detailed
system specification. requirements for a system, during the design process
to describe the system to engineers implementing the system and after im-
plementation to document the systems structure and operation.

### Entity Relational Model Diagram

An entity relationship model is usually the result of systematic analysis to
define and describe what is important to processes in an area of a business. It
does not define the business processes; it only presents a business data schema
in graphical form. It is usually drawn in a graphical form as boxes (entities)
that are connected by lines (relationships) which express the associations
and dependencies between entities. An ER model can also be expressed in
a verbal form, for example: one building may be divided into zero or more
apartments, but one apartment can only be located in one building. Entities
may be characterized not only by relationships, but also by additional prop-
erties (attributes), which include identifiers called primary keys. Diagrams
created to represent attributes as well as entities and relationships may be
called entity attribute-relationship diagrams, rather than entity-relationship
models. An ER model is typically implemented as a database. In a sim-
ple relational database implementation, each row of a table represents one
8instance of an entity type, and each field in a table represents an attribute
type. In a relational database a relationship between entities is implemented
by storing the primary key of one entity as a pointer or foreign key in the
table of another entity. This system have these entities ** need to describe our own prject entity ** , ** requierd the EER Model Diagram **

### EER Model Diagram
The EER model includes all of the concepts introduced by the ER model.
Additionally it includes the concepts of a subclass and superclass (Is-a),
along with the concepts of specialization and generalization. Furthermore, it
introduces the concept of a union type or category, which is used to represent
a collection of objects that is the union of objects of different entity types.
** figure EER Model Diagram **

### Use Case Diagram
A use case diagram at its simplest is a representation of a users interaction
with the system that shows the relationship between the user and the different
use cases in which the user is involved. A use case diagram can identify
the different types of users of a system and the different use cases and will
often be accompanied by other types of diagrams as well.Users Actor Info:
Name: User Description: The project manager that want to invite the other
developer and have right ot create project and add the histories in the project.
Actor Info: Name: User Description: All the company and other people
which want ot estimate their projects. system: Actor Info: Name:System
Description The system that will calculate the story points and summarize
the story points.
** fiqure User Case Diagram ** 

### Activity Diagram
Activity diagrams are graphical representations of workflows of stepwise ac-
tivities and actions with support for choice, iteration and concurrency. In the
Unified Modeling Language, activity diagrams are intended to model both
computational and organizational processes (i.e. workflows). Activity dia-
grams show the overall flow of control. Activity diagrams are constructed
from a limited number of shapes, connected with arrows.The most important
shape types: rounded rectangles represent actions; diamonds represent deci-
sions; bars represent the start (split) or end (join) of concurrent activities;
a black circle represents the start (initial state) of the workflow an encircled
black circle represents the end (final state). Arrows run from the start to-
wards the end and represent the order in which activities happen [8]. Activity
diagrams may be regarded as a form of flowchart. Typical flowchart tech-
niques lack constructs for expressing concurrency However, the join and split
symbols in activity diagrams only resolve this for simple cases; the meaning
of the model is not clear when they are arbitrarily combined with decisions
or loops. While in UML 1.x, activity diagrams were a specialized form of
state diagrams, in UML 2.x, the activity diagrams were renormalized to be
based on Petri net-like semantics, increasing the scope of situations that can
be modeled using activity diagrams.[7] These changes cause many UML 1.x
activity diagrams to be interpreted differently in UML 2.x [2].