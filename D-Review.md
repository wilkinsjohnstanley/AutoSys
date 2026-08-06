### Which JIL action is used to modify an existing job definition without deleting and recreating it?
* update_job: modifies attributes of an already existing job definition in-place without removing its history or dependencies
Others include:
* insert_job: Creates a brand new job definition from scratch
* delete_job: Removes an existing job definition from the database.
In Job Information Language (JIL) (used by workload automation tools like Broadcom Autosys) different sub-commands control job definitions in the database. 
