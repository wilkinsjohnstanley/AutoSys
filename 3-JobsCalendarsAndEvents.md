# Understanding Basic Autosys Terminology
### Jobs
In Autosys, a job is a unit of work that is scheduled and executed by the system. Jobs can represent various tasks, such as running a script, executing a program, or performing a database query. Each job is defined with specific attributes, including it's name, command, schedule, and conditions for execution.
### Key Attributes of a Job
* Job Name: A unique identifier for the job.
* Command: The specific task or script the job executes.
* Schedule: The time or frequency at which the job runs.
* Dependencies: Conditions that must be met before the job can execute.

### Real-World Example: Automating Batch Processes
Imagine a retail company that needs to process daily sales data. An Autosys Command Job can be created to execute a script that aggregates sales data from multiple sources and generates a report. The job can be scheduled to run every night at 11:00PM, ensuring the report is ready for the next business day.
### Job Types
AutoSys supports different types of jobs, each designed for specific purposes. Understanding these job types is essential for effective scheduling and automation.
### Common Job Types
* Command Job: Executes a command or script on a specified machine.
* File Watcher Job: Monitors the presence, modification, or deletion of a file.
* Box Job: A container for grouping multiple jobs. Box jobs allow you to organize and control the execution of related jobs.
* Database Job: Executes SQL queries or database-related tasks.

### Real World Example: Monitoring File Changes
A financial institution uses a File Watcher Job to monitor the arrival of transaction files from external systems. When a new file is detected, the job triggers a downstream process to validate and import the data into the database. This ensures timely processing of critical financial transactions.
### Calendars
Calendars in Autosys define specific dates and times when jobs are allowed to run. They help in scheduling jobs based on business requirements, holidays, or other time-based constraints.
### Key Features of Calendars
* Custom Dates: Define specific dates for job execution
* Recurring Patterns: Set up recurring schedules, such as daily, weekly, or monthly.
* Exclusions: Specify dates when jobs should not run, such as holidays.
### Real-World Example: Managing HOliday Schedules
A manufacturing company uses Autosys Calendars to ensure that production-related jobs do not run on public holidays. For example, a job that generates inventory reports is scheduled to run every weekday, but the calendar excludes national holidays to avoid unnecessary processing.
### Events
Events in Autosys are triggers that initiate specific actions or changes in job status. Events are used to manage job depdencies and workflows effectively.
### Common Event Types
* STARTJOB: Triggers the execution of a job
* SUCCESS: Indicates that a job has completed successfully.
* FAILURE: Indicates that a job has failed.
* ON_HOLD: Pauses the execution of a job until further notice
* OFF_HOLD: Resumes the execution of a job that was previously on hold.

### Real-World Example: Managing Dependencies
A logistics company uses Autosys Events to manage job depdencies. For instance, a job that updates shipment tracking formation is truggered by a SUCCESS event from a preceding job that processes incoming shipment data. This ensures that tracking updates occur only after the data is successfully processed. 
### Summary
Autosys provides a robust framework for job scheduling and automation. Key components include jobs, job types, calendars, and events, each playing a vital role in ensuring efficient workflows. By understanding these terms and their real-world applications, users can effectively manage and optimize their Autosys environment.
### Next Steps
To gain a deeper understanding, consider exploring advanced Autosys topics such as job dependencies, error handling, and additional real-world use cases.

























