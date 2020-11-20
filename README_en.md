# Initial estimate of a software development project.
**Work in progress (90%)**

## 1. Introduction.
The idea of ​​doing this work arose after virtual attendance at conferences and talks of some Latin communities of developers that I found on Twitter, in which the question is frequently asked, **How do I estimate a project?** There are (very good) videos and articles dealing with the subject, but none of them are a complete exercise, and therefore, I consider that the question still has no answer (at least that I know of).

My intention is to develop the different activities that are required to **make an initial estimate (of time and cost) of a project**, which serves as a complete and practical example for a **freelancer** (who generally works alone).

This work is based on the **Cascade model**, why? Because of the tools used. Based on my experience, software development projects are always for yesterday, with strong time and cost constraints and a lot of uncertainty regarding requirements. After an initial estimation we can determine if the software development is directed by the Cascade model or in an agile way with SCRUM, for example.

I am not married to any methodology, if something from one works to another, use it, nobody is going to put you in jail for that, the objective is to have a software that satisfies the client's requirements, within the established time and budget (haha, this is academic theory). And remember, **this is an initial estimate based on your current knowledge** of the project in question, **make this very clear to the client**, many take this estimate as the final cost of the project.

**You have to be able to define (for the good of the Client and the Developer) when a product is finished and when the scope has varied and you have to charge more and take more time to do it.**

## 2. Tools used.
1. [OSRMT 1.8](https://sourceforge.net/projects/osrmt/)<br>
Open Source Requirements Management Tools, a desktop application that allows defining Capabilities (Features), Requirements, Design, Implementation and Test Cases, based on Cascade.
There is a [nimble](https://sourceforge.net/projects/nimble/) web version that supports Cascade and Agile, but it is more complex to install and configure, so I will not use it here.

2. [StarUML 3.2.2 (evaluation edition)](http://staruml.io/)<br>
Desktop application that allows you to create UML 2.0 diagrams and models.

3. [ProjectLibre 1.9.2 (community edition)](https://www.projectlibre.com/)<br>
Desktop application that enables waterfall-based project planning and management.

4. [LibreOffice](https://www.libreoffice.org/discover/libreoffice/)<br>
Applications for Spreadsheets and word processing, among others.

**Even if you don't install the tools used, you can review image or pdf files created for this purpose (see Appendix A3.2).**

## 3. Initial interview with user.
I found a video on [YouTube](youtube.com) that explains a way to carry out a **preventive maintenance plan for machinery** , so well developed that it occurred to me to use it as an example of an initial interview with a fictitious user who requires software that allows him to make and execute the plan and hires you to do the development. It has enough elements to show the different aspects to consider in a software development project.

Before continuing, I invite you to watch the following video [7 PASOS PARA REALIZAR UN PROGRAMA DE MANTENIMIENTO | Iso 9001](https://www.youtube.com/watch?v=umnJt1e9lWM)

*I propose you a challenge, estimate the time and cost of software development for this client, from a bird's eye view, without any analysis like the one we are going to develop here, write it down. Now, do the full exercise and see how much time and cost you get. You may be surprised at the difference.*

The estimation process is iterative, you do not perform one task and then another. All the elements are being built little by little since they are very interrelated. While defining a Functional Requirement, a possible risk occurs to you, or something that would be out of reach. When you are estimating, you realize that you are missing a Requirement or a Definition or a Non-functional Requirement, etc.

**The estimation begins by determining the functionalities and the requirements associated with them. I also need to define the acceptance tests, what things seem to be out of scope, as well as definitions (all this in OSRMT). Along with this I am identifying risks (spreadsheet), and the domain model (staruml). You can build the work breakdown structure (ProjectLibre), but I prefer, once I have everything defined in OSRMT, export the data to a CSV file, group and order and then paste the list in ProjectLibre, to make the estimates of time and cost.**

Have you heard of **Analysis Paralysis** ? It's a mistake made that you never really start working on, because you never finish analyzing. Take your analysis to reasonable detail, where you feel comfortable and allow you to make a realistic estimate.

### 3.1 Notes from the initial interview.
These are my notes obtained during the initial interview.

```
ISO 9001

1. Identification of machines, assigning a code
    a) process code PRoduction, LOGISTICS, QUALITY, MAINTENANCE
    a.1) optional thread
    b) code for being a machine: Machine, Monitoring and Measurement team
    c) consecutive by machine type: Stamping-01, Laser-02
    d) consecutive by quantity: sequential

2. List of machines:
    Data: Machine, Code (step 1), Brand, Model, Serial No., [Location,] Status [Active, Maintenance]

3. Identify the machines:
    a) Labeling (sticky), Marking (paint)
    Data: Machine name, code

4. Create preventive maintenance plan
    a) Periodicity: Daily, Weekly, Biweekly, Monthly, Bimonthly, Quarterly, Semiannual, Annual
    b) format: mm-format-plan_manto.png

5. Create preventive maintenance sheet (individual per machine - mm-format-sheet_manto.png)
    a) archive card every time maintenance is performed
    b) maintenance activities. performed by operator or maintenance personnel

6. Create corrective maintenance file
    Data: same data as preventive maintenance
           Comments about machine failure
           Reporting person
           Report date
           Maintenance performed
           Machine delivery date
           Responsible for maintenance

7. Create maintenance folder by machine

Machine's user manual
```

Each of the numbers in the list above will be a System Capability.

## 4. Identification of things that are outside the scope of the project.
Here put things that you identify and that the client has not mentioned, it is very likely that they have taken them for granted, and when you present the proposal (or before, if possible), ask the client if they want to include them in the project (then they will become in capabilities and requirements).

## 5. Non-functional requirements.
Use the **FURPS+** classification (I use the indicated mnemonics). Normally, non-functional requirements are geared towards the complete system rather than individual capabilities.

KIND|DESCRIPTION|MNEMONIC
-|-|-
Usability|	fUrps - Usability|	USES
Human factors|		|HFA
Aesthetics|		|AES
UI consistency|		|UIC
Context Help|		|CHP
Wizard|		|WIZ
User documentation|		|DOC
Traning material|		|TRA

KIND|	DESCRIPTION|	MNEMONIC
-|-|-
Reliability	|fuRps - Reliability|	REL
Frequency of failure|		|FRF
Severity of failure|		|SVF
Recoverability|		|REC
Predicatability|		|PRE
Accuracy|		|ACC
MTBF|		|MTBF

KIND|	DESCRIPTION|	MNEMONIC
-|-|-
Performance|	furPs - Performance|	PER
Speed|		|SPD
Efficiency|		|EFF
Availability|		|AVA
Accuracy|		|ACCU
Throughput|		|THR
Response time|		|RSP
Recovery time|		|RCT
Resource usage|		|MSW

KIND|	DESCRIPTION|	MNEMONIC
-|-|-
Supportability|	furpS - Factors during / after implementation	SUP
Testability|	Mocks|	TST
Extensibility|		|EXT
Adaptability|		|ADP
Maintainability|		|MAI
Compatibility|	Web, Client, OS, Server	|COM
Configurability|		|CNF
Serviceability|	patches	|SRV
Instalability|	setup	|INS
Localizability|	I18N	|LOC
Scalability|		|SCA

KIND|	DESCRIPTION|	MNEMONIC
-|-|-
Design|	MVC, N layers, OOP, Structured, Distributed	|DES
Implementation|	Standards, Frameworks, Language, Operating environment	|IMP
Interface|	Web services, Protocols, File formats	|INT
Physical|	Hardware	|PHY

## 6. Capabilities and functional requirements.
### 6.1 Features.

KIND|	DESCRIPTION|	MNEMONIC
-|-|-
Feature|	A Capability the system must provide|	FEA
Out of scope|	Things outside the scope of the project	|OOS
Definition|	A definition for Data Dictionary	|DEF
Fact|	A thing that is known or proved to be true	|FAC
Law|	Law	|LAW
Policy|	Business policy	|POL
SLA|	Service Level Agreement	|SLA
Rule|	Rule	|RUL
Assumption|	Assumption	|ASS

### 6.2 Functional requirements.

KIND|	DESCRIPTION|	MNEMONIC
-|-|-
Functional Requirement|  A requirement the system must provide	|FUN
Security|	Security is a functional requirement|	SEC

### 6.3 Final products (deliverables / outcomes).

KIND|	DESCRIPTION|	MNEMONIC
-|-|-
Prod-Screen|	Screen	|PSCR
Prod-Report|	Report	|PREP
Prod-Process|	Data processing	|PPRO
Prod-Artifact|	PDF file, CSV, Document	|PART
Prod-Service|	SOAP, Rest	|PSER

### 6.4 Traceability.
Traceability establishes a relationship between artifacts, which begins in Capabilities that are translated into Requirements, which give rise to Designs that are Implemented and must be Tested. It facilitates the impact analysis when a change is requested, as well as the identification of the origin of an artifact (justification of why it exists).

### 6.5 Dependency.
It is the relationship that exists between artifacts, which allows us to identify what comes before what, or what has to be done before considering something as finished. It is represented by an array of dependencies and is useful for prioritization (you can't build a roof if you don't have walls to support it). This task is done when you start to design the system, there is no point in doing it for the initial estimation.

## 7. Domain Model.
It is very important, as it allows you to identify actors, objects (entities), relationships and dependencies between objects, etc. Based on it, you can determine the complexity of each functional requirement, operations to be performed, attributes by objects, etc.

*mm-domain.mdj (StarUML)*

The classes with a white background color are those identified in the initial interview. Classes with a blue background correspond to things that are currently out of scope. The classes with a yellow background are copies of the original (white), I use them to avoid crossing lines in the model.

## 8. Prioritization.
The initial requirements will be part of version 1.0, from there more modules will be added (those that are out of scope, if the client accepts them) or new requirements. After the initial proposal, the priority of each of the capacities to be developed must be determined.

## 9. Risks.
Risk analysis is a very important part, because if you identify a risk of medium or high impact that cannot be eliminated, perhaps you should not continue with the execution of the project.

Initially all risks have high priority, in the presentation of the proposal (or earlier if possible), the probability of occurrence is clarified and its impact is determined, modifying its status and the actions to be implemented.

In the file *mm-analisis_riesgos.ods* (Libre Office) I present the corresponding analysis. Risks should be monitored during software development, as their status can change, as well as new ones.

Probability|	Meaning
-|-
0|	Risk cannot occur
100|	Risk is sure to occur

Impact|	Meaning
-|-
0|	The occurrence of the risk does not affect the project.
100|	The occurrence / non-mitigation of the risk can impede the success of the project.

Reply|	Meaning
-|-
Avoid|	Take action to eliminate the cause or effects of the hazard.
To transfer|	Transfer the risk to a third party.
To mitigate|	Take actions to reduce the probability of occurrence or impact of the risk.
To accept|	No action is taken until the risk occurs.

## 10. Estimation of time and costs.
Remember, **this is an initial estimate**, in circumstances of **high uncertainty** since you have only had one interview with the client, and it should be updated as the project progresses, mainly due to changes in scope and requirements.

Calculate costs for the implementation of things that are outside the scope of the project and the resolution of risks, so that you know how much more the project will cost if they are included, so you can also immediately report the extra cost, when the client tell you that they do want to include something you propose.

It includes **ALL** the activities to be carried out during the project, presentations, meetings, reading of the client's own documents, research and testing of API or WSDL, installation and configuration of application or database servers, quotes, user training, writing of manuals, modules not specified by the client but you know you have to do them (menus, application configuration, contextual help, access control) etc. **Remember that in Mexico there is the Law on Protection of Personal Data Held by Private Parties**, if you save user data, you must adhere to this law.

There are times when you will have to import existing data to the new system, they can be in CSV, Database, TXT. Estimate the ETL process time to import into the new system. You will need to validate the integrity of the data.

Do you have to learn something new? Estimate time, not cost, unless it is specific knowledge for this client.

Of course, it includes the time it takes to prepare the initial proposal.

To estimate time to do something, consider the following:
a) You know how to do it and you have done it before,
b) You have not done it, but you know how it is done,
c) You have no idea how it is done.

In the file *mm-estimations.pod* (ProjectLibre) I present the work breakdown structure and estimation of time and costs.

### 10.1 Fixed costs.
#### 10.1.1 Electricity, telephone, internet, office rent.
Divide the monthly amount of each of these concepts by 30.4, this is the daily amount you pay, charge it to the project, for the days you dedicate to it.

#### 10.1.2 Amortization of equipment (computers, printers).
In accounting terms (in Mexico) these equipments have a useful life of two years. Divide the purchase value by 24 and you will have the monthly depreciation of your equipment. Upload it to the project, for the months you dedicate to it.

#### 10.1.3 Software licenses.
It includes the purchase of software licenses and monthly/annual subscription payments that you make to GitHub, Heroku, mailtrap, Notion and all the software you use to do your work. Likewise, calculate the monthly amount and charge it to the project, for the months you dedicate to it.

#### 10.1.4 Utility
Determine the percentage of profit you want to obtain and include it in the costs.

## 11. Proposal
In the file mm-proposal.odt (Libre Office) I show you an example of a proposal, which, once accepted, will lead to the signing of a contract.

## Appendix 1 - Agility
Even though I took a **Scrum Master** course and have read several books and watched dozens of videos, I still cannot find answers to the following (so, to be honest, I did not certify, like all my fellow students):

a) **experimentation** - you barely have time to finish, almost always the code is left as it came out the first time.

b) **failure early** - associated with experimentation, do you have time to fail?

c) **welcome changes** - really how quickly can you respond to changes? Even with SOLID, Design Patterns, Software Architecture, etc. How many times do you agree to change something?

d) **MVP** - for me, what has value for the customer, has dependencies, and you have to develop those dependencies before you can give it something of value.

e) **estimates by points** - that do not equal time! So how do you know how many Sprints you are going to need?

f) **estimates made by a team that does not yet exist during an initial estimate.**

With these doubts I already understood what the agile mindset is, it is not just repeating words, it is something much more complex.

Obviously I need to participate in an agile project, or a brain formating :)

## Appendix 2 - Microadministration.
Do not fall into the trap of Micro-administration, you will hang yourself. Micromanaging is recording so many things that it takes you longer to do it than it takes to build the software. The minute record of what you do is very common in consulting companies, where you have to justify your time with blogs. Your client cares about the software, not your blog, and if he asks for it, clarify that it will cost him and the project will take more time to complete .

## Appendix 3 - Resources.
### A3.1 Tools.
[OSRMT 1.8](https://sourceforge.net/projects/osrmt/)

[ProjectLibre](https://sourceforge.net/projects/projectlibre/)

[ProjectLibre Tutorial](https://www.youtube.com/watch?v=9xwR4JCBaIU&feature=youtu.be)

[StarUML](http://staruml.io/)

[LibreOffice](https://www.libreoffice.org/discover/libreoffice/)

[mdbtools](https://github.com/mdbtools/mdbtools) ```sudo apt-get install mdbtools``` para extraer la tabla *ARTIFACT* de *starter.mdb*
```mdb-export starter.mdb artifact >requerimientos.csv```

### A3.2 Analysis files.
In the analysis folder:
1. mm-format-sheet_manto.png Image of the maintenance sheet format used by the client.
2. mm-format-plan_manto.png Image of the Maintenance Plan format used by the client.
3. starter.mdb Access database used by OSRMT, contains the Capabilities, Requirements and Acceptance Tests lists.
4. mm-requirements.csv List of Capabilities and Requirements extracted from starter.mdb .
5. mm-domain.jpg Image of the domain diagram. Corresponds to mm- domain.mdj from StarUML.
6. mm-risk_analysis.pdfRisk analysis pdf file. Corresponds to mm-risk_analysis.ods from LibreOffice.
7. mm-estimating.pdf Pdf file of the calculation of time and costs. Corresponds to mm-estimation.pod of ProjectLibre.
8. mm-proposal.pdf PDF file of the initial proposal. Corresponds to mm-proposal.odt from LibreOffice.

### A3.3 Books:
1. OpenProj The open source solution for managing your projects, Lisa A. Bucki
2. Mastering Non-Functional Requirements, Sameer Paradkar, Packt Publishing
3. SWEBOK 3.0 IEEE Computer Society
4. BABOK 3.0, International Institute of Business Analysis
5. PMBOK 5th edition, Project Management Institute, Inc.
6. Practice Standard for Project Risk Management, Project Management Institute, Inc.
7. Practice Standard for Work Breakdown Structures 2nd Edition, Project Management Institute, Inc.
8. Practice Standard for Project Estimating, Project Management Institute, Inc.
9. Systems Analysis and Design 8th Edition, Kendall & Kendall, Pearson
10. Software Engineering 9th Edition, Sommerville, Pearson
11. The Unified Modeling Language (UML 2.0), Grady Booch James Rumbaugh, Ivar Jacobson, Addison Wesley
12. The Unified Modeling Language - Reference Manual (UML 2.0), Grady Booch James Rumbaugh, Ivar Jacobson, Addison Wesley

### A3.4 Related Videos:
1. Laura Ribas. [Cómo poner el precio correcto a tus productos/servicios](https://www.youtube.com/watch?v=2Lg14wmlQwI&feature=youtu.be)
2. Hector De León. [¿Cuánto cobrar como programador freelance? Ejemplo paso a paso](https://www.youtube.com/watch?v=UrocE07Bev4)
3. Hector De León. [¿Cómo cobrar un proyecto de software?](https://www.youtube.com/watch?v=sdAiDJt-1lA)
4. Fernando Herrera. [Cuánto cobrar por un trabajo](https://www.youtube.com/watch?v=Dc0PgJm3KA0&feature=youtu.be)
5. Rodolfo Borja. [Calcular el costo por hora](https://www.youtube.com/watch?v=2Ogj2Wp6TGU)
6. Rodolfo Borja. [Cómo estimar las horas de un proyecto](https://www.youtube.com/watch?v=xo_HFjYkgS8)
7. Rodolfo Borja. [Cómo hacer la propuesta de un proyecto](https://rborja.net/como-hacer-una-propuesta-de-software/)

**eof**