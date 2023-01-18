
The name DevOps is derived from combination of Development + Operations.

## Need For DevOps

The most common requirement for software changes are:

-   Unpredictable time of occurrence.
    
-   Quick deployment of software changes.

The ability of an organization to thrive in an environment, that requires it to respond to all the unanticipated changes as quickly as possible, is called as **Business agility**.

DevOps can be any initiative which is focused on enabling business agility by:

-   Eliminating barriers between development team and operations team in agile projects to eliminate delays
-   Moving deliverables through all phases development life cycle faster
-   Ensuring, always there is no compromise on deliverable quality.

While in traditional Team work due to this isolation, there are following barriers that exist:
- Process barriers 
- Co-ordination and communication barriers
- Cultural barriers

## The Team Structure in DevOps

### Traditional (waterfall) Team work

![[Pasted image 20230118095438.png]]

**Characteristics**

-   **Resource utilization**: The QA team needs to wait during the time the development team is coding. The operations team need to wait until the QA team finishes testing.
    
-   **Inter-team relationship**: Since each team has its own specific goals and timelines to meet, conflicts are bound to happen. Whenever there are defects or missed deadlines, each team blame the others. This results in loss of productive time which is spent on conflict resolution.
    
-   **Turnaround time**: Since there are two levels of inter-team handovers involved, there is additional time consumed at each level for documentation, reviews and sign-offs.


### Agile Team Work
![[Pasted image 20230118095501.png]]

**Characteristics**

-   **Resource utilization**: The developers and testers work in parallel and are always engaged. However the operations team needs to wait for the agile team until they come up with the working build. 
    
-   **Inter-team relationship**: Since the developers and testers are cross skilled in each other's tasks and share same goals and deadlines, there is very less chance of conflicts between them. Instead they work together and stand-in for each other whenever the need arises. However the conflicts with the operations team are bound to happen as earlier.
    
-   **Turnaround time**: Since a lot of time and effort spent on communication and handover processes is eliminated, agile teams can deliver faster than traditional teams. However, there is still additional effort that goes into communication and handover processes with the operations team

### DevOps teams work

![[Pasted image 20230118100216.png]]

**Characteristics**

-   **Resource utilization**: Since there is no skill-wise separation of developers, testers and operations, there are no idle resources. The team size is usually very small in which anyone can do any development, quality assurance or operations tasks.
    
-   **Inter-team relationship**: The DevOps team works as a single unit, with the same goals and deadlines. Hence work conflicts between team members are non-existent.
    
-   **Turnaround time**: DevOps teams can deliver builds a lot faster than traditional or agile teams.

## The aspects of DevOps

DevOps uses **Continuous Delivery Pipeline** strategy, enables a constant flow of code changes into production.

![[Pasted image 20230118100750.png]]

### Agile Development

-   Create code to add new features, fix defects, enhance features or to act on the feedback received from other aspects.
    
-   Once the developers from each module/service team checks in their code, trigger **automated compiling and build creation**.
    

### Continuous Integration

-   Once a build is ready and available in the pipeline, trigger **automated integration** with the overall application code base.
    

### Continuous Testing

-   Once the code is ready, trigger **automated unit tests**, static code analysis and report the results.
    
-   Before the code in integrated, trigger **automated integration tests** and report the results.
    
-   Once the code is integrated, trigger **automated functional and non-functional system tests** and report the results.
    

### Continuous Deployment

-   Once a build in the pipeline has successfully passed all the tests, trigger its **automated deployment** into production. 
    
-   Keep deploying all the tested builds in the sequence they were pushed into the pipeline.
    

### Continuous Monitoring

-   Continuously keep collecting information that needs the team's attention, from the domain of every aspect, for all the builds and trigger **automated intimation** to the concerned team.

