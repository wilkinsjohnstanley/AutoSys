### Which JIL action is used to modify an existing job definition without deleting and recreating it?
* update_job: modifies attributes of an already existing job definition in-place without removing its history or dependencies
Others include:
* insert_job: Creates a brand new job definition from scratch
* delete_job: Removes an existing job definition from the database.
In Job Information Language (JIL) (used by workload automation tools like Broadcom Autosys) different sub-commands control job definitions in the database. 

### Box Jobs
A Box Job is used to group and control related jobs as a unit. 

In Autosys, a Box Job is a container used to logically group and mange a collection of dependent or related jobs. The entire group can be started, stopped, or monitored collectively, allowing you to orchestrate complex operational workflows and manage execution dependencies under a single parent entity. 

In workload automation tools like Broadcom AutoSys, a box job acts as a container for other sub-jobs. When a box job's own conditions are met, the box changes its status to RUNNING. Any jobs inside that box that do not have their own specific job-level starting conditions will immediately inherit the starting signal. Because they have no conditions restricting them from running relative to each other, they all become eligible to start simultaneously and will run in parallel, subject to available system resources and machine limits. 

### autorepo
autorep is the primary command used to generate reports about job definitions, execution status and history. 

Other commands include:
* jil : to define, modify, or delete AutoSys objects (like jobs, machines, or resources)
* sendevent: sends administrative events to the AutoSys event processor (such as STARTJOB, FORCE_STARTJOB, or KILLJOB)
* autoping: used to verify connectivity to AutoSys components (like Event Server or Remote Agents).



### STARTJOB vs FORCE_STARTJOB
FORCE_STARTJOB can bypass normal starting conditions, while STARTJOB respects them.

* STARTJOB: Instructs the system to start a job, but it respects all defined dependencies and normal starting conditions (such as lookback periods, time windows, and job resource availability). If those conditions are not met, the job will not runimmediately.
* FORCE_STARTJOB: Instructs the system to immediately execute the job by bypassing the evaluation of normal starting conditions and dependencies. It forces the job into a running state regardless of whether its predecessor jobs have completed successfully.

### Event Server
The AutoSys component responsible for storing job definitions and job events is the Event Server.

In Broadcom's AutoSys Workload Automation architecture, the architecture functions through several distinct core components.
* Event Server (Database): This is the central repository (often a relational database instance like Oracle, Sybase, or MS SQL Server) that stores all job definitions, configuration information, and historical job events.
* Event Processor: This component acts as the execution engine. It reads events from the Event Server, interprets the job definitions, routes tasks to agents and updates the Event Server with new status events.
* Remote Agent: This is a lightweight process running on target execution machines. It accepts commands from the Event Processor, starts the local jobs, monitors them, and reports exit codes back.
* WCC (Workload Control Center): This provides the graphical user interface (GUI) management console for users to design, monitor, and manage workflows visually.

### Job Dependencies: success(job_A)
In AutoSys, the condition success(job_A) means that job_B runs only if job_A ends successfully.

In AutoSys workload automation, job dependencies control the execution flow of processes. The success keyword defines a conditional dependency requiring the target job to complete with a SUCCESS status before the dependent job can be triggered.
* success(job_A): Triggers job_B only when job_A finishes with a normal, successful exit code.
* failure(job_A): Triggers the next job if the target job terminates abnormally.
* terminated(job_A): Triggers the next job if the target job is manually killed or stopped.
* done(job_A): Triggers the next job regardless of whether the target job succeeded or failed.

### date_conditions
In AutoSys Job Information Language (JIL), the date_conditions attribute acts as a master toggle that tells the event processor whether or not to evaluate time-based and date-based scheduling criteria (such as start_times, start_mins, days_of_week, or run_calendar).


























