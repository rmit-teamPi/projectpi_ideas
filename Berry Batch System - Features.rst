=============================
Berry Batch System - Features
=============================

Primary Set of Features
-----------------------

1) The "masterpi" will have a state table, with current states for each "slavepiX" node.
2) The "masterpi" will send the job (script etc...) to the next available "slavepiX" node.
3) The "slavepiX" will process the job and returns an exit code once it has finished processing.
4) The "masterpi" will update its state table.

99) The "masterpi" will monitor memory usage of each "slavepiX" node, to ensure that memory leaks are detected.


Additional Set of Features (if time permits)
--------------------------------------------

1) The Berry Batch "masterpi" will monitor the CPU utilization of the "slavepiX" nodes. When the utilization, reaches 
   a preset level the "masterpi" will send a job to the next available "slavepiX" node. The "slavepiX" processes the
   job and returns an exit code once it has finished processing.

2) Caching system - The "masterpi" will calculate an MD5 hash of each job and perform a lookup to determine whether one 
   of the "slavepiX" nodes has already processed that job before. If it has, the job will be sent to the appropriate Pi,
   therefore reducing the network overhead as the job (script etc...) won't need to be sent again.
   
3) Priority system - The "masterpi" will monitor the clock speed of each "slavepiX" node. Nodes with a higher clock speed 
   will be sent jobs with a high priority.

4) Automatically assign hostname - When a new "slavepiX" is connected to the network, the "masterpi" automatically assigns
   it a new hostname.
