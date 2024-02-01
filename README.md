 

DBMS ASSIGNMENT: 

“EFFECTIVE TIME MANAGEMENT FOR PROJECT” 

                                       			                                    By: Joel C Raju		 

 

DOMAIN DESCRIPTION: 

Effective time management is crucial for the success of any project. It involves planning, organizing, and allocating resources in a way that optimizes productivity, meets deadlines, and achieves project goals. Here are key principles and practices for effective time management in projects: 

Time management in project management is essential to dividing resources effectively to ensure teams produce high-quality work within the agreed-upon deadline. 

 

BACKGROUND STUDY: 

To understand the “Effective time management for project” domain, I started to read about the domain and what it’s trying to achieve. Also learnt how the relevance of the domain during the development process.  

To learn more about the domain, I tried out Nulab and Kanban Board which are time management tools that help to organize and prioritize tasks to achieve the team goal faster. It also increases productivity among the team by reducing the confusion among team members regarding the tasks assigned. 

PROJECT WORKFLOW: 

From the background study, A team is allocated a board in which there will be tasks written in cards. The Team members will be allocated the tasks along with deadline and must set the task status according to their progress. This way the team will work efficiently while keeping track of everyone’s task. 

 

REQUIREMENT ANALYSIS: 

The requirement analysis involves understanding and delineating the needs, objectives, and functionalities related to effective time management for projects. Requirement analysis for the “Effective time management for projects” domain are: 

<b>Task Allocation Mechanism:</b> Allocating Tasks to Teams: This reveals a specific requirement for a system that allows easy allocation and tracking of tasks within a team. 

 

<b>Task Status Tracking:</b> This indicates a requirement for a system that supports real-time task status updates and tracking. 

 

<b>Efficient Team Collaboration:</b> Reducing Confusion, this points to a requirement for collaborative tools that enhance team communication and coordination. 

 

<b>Deadline Setting:</b> This allows team to follow a timeline and complete the work before reaching the 	deadline. 

 

E-R DIAGRAM: 

 

 

DETAILED EXPLAINATION: 

<b>Project Table (Project):</b> 
<ul>


<li>projetc_id: Primary key, VARCHAR(10), not null - Unique identifier for the project. </li>

<li>project_name: VARCHAR(30), not null - Name of the project. </li>

<li>start_date: DATE, not null - The start date of the project. </li>

<li>end_date: DATE - The end date of the project. </li>

<li>description: VARCHAR(100) - Description of the project. </li>

<li>status: VARCHAR(20) - Status of the project. </li>

<li>project_created: DATE, not null - Date when the project was created. </li>

<li>project_created_by: VARCHAR(30), not null - User who created the project. </li>

 </ul>

<b>Task Table (Task):</b> 
<ul>

 <li>task_id: Primary key, VARCHAR(10), not null - Unique identifier for the task. </li>

<li>project_id: Foreign key referencing Project.project_id, VARCHAR(10), not null - Identifier of the project to which the task belongs. </li>

<li>task_name: VARCHAR(30), not null - Name of the task. </li>

<li>task_description: VARCHAR(100) - Description of the task. </li>

<li>start_date: DATE, not null - The start date of the task. </li>

<li>end_date: DATE - The end date of the task. </li>

<li>status: VARCHAR(20) - Status of the task. </li>

<li>task_created_by: VARCHAR(30), not null - User who created the task. </li>

</ul>

<b>Users Table (Users):</b>
<ul>
<li>user_id: Primary key, VARCHAR(10), not null - Unique identifier for the user. </li>

<li>username: VARCHAR(30), not null - User's username. </li>

<li>email: VARCHAR(30), not null - User's email address. </li>

<li>password: VARCHAR(30), not null - User's password. </li>

<li>account_created: DATE, not null - Date when the user account was created. </li>

 </ul>

<b>TaskAssignment Table (TaskAssignment):</b> 
<ul>

 <li>assignment_id: Primary key, VARCHAR(10), not null - Unique identifier for the task assignment.  </li>

<li>task_id: Foreign key referencing Task.task_id, VARCHAR(10), not null - Identifier of the task being assigned.  </li>

<li>user_id: Foreign key referencing Users.user_id, VARCHAR(10), not null - Identifier of the user to whom the task is assigned.  </li>

<li>assignment_date: DATE, not null - Date when the task assignment was created.  </li>

<li>completion_date: DATE - Date when the task was completed.  </li>

<li>status: VARCHAR(20), not null - Status of the task assignment.  </li>

 </ul>

<b>UserRole Table (UserRole):</b> 
<ul>
<li>user_role_id: Primary key, VARCHAR(10), not null - Unique identifier for the user role. </li>

<li>user_id: Foreign key referencing Users.user_id, VARCHAR(10), not null - Identifier of the user associated with the role. </li>

<li>user_role: VARCHAR(20), not null - Role assigned to the user. </li>
</ul>
 

 

 

NORMALIZATION PROCESS: 

Normalization is a database design process that aims to minimize data redundancy and dependency by organizing tables in a way that reduces or eliminates data anomalies. The standard normal forms are First Normal Form (1NF), Second Normal Form (2NF), and Third Normal Form (3NF).  

  

Let's analyze how the provided tables align with normalization principles:  

 

First Normal Form (1NF): 

All tables have atomic (indivisible) values in each field. 

There are no repeating groups or arrays in any field. 

Second Normal Form (2NF): 

In the Task table: 

All non-key attributes are fully functionally dependent on the primary key (task_id). 

The project_id is a foreign key, and other attributes are dependent on the entire primary key. 

In the TaskAssignment table: 

All non-key attributes are fully functionally dependent on the primary key (assignment_id). 

Both task_id and user_id are foreign keys, and other attributes are dependent on the entire primary key. 

In the UserRole table: 

All non-key attributes are fully functionally dependent on the primary key (user_role_id). 

The user_id is a foreign key, and other attributes are dependent on the entire primary key. 

Third Normal Form (3NF): 

In the Project table: 

The project_created_by field is dependent only on the primary key (projetc_id). 

There are no transitive dependencies. 

In the Task table: 

The task_created_by field is dependent only on the primary key (task_id). 

There are no transitive dependencies. 

In the TaskAssignment table: 

The status field is dependent only on the primary key (assignment_id). 

There are no transitive dependencies. 

In the Users table: 

No transitive dependencies; all non-key attributes depend directly on the primary key (user_id). 

In the UserRole table: 

The user_role field is dependent only on the primary key (user_role_id). 

There are no transitive dependencies. 

 

Overall, the provided tables appear to be in at least 3NF, as there are no transitive dependencies, and each non-key attribute is dependent on the whole primary key. This structure helps in reducing redundancy and maintaining data integrity. 

 

 
