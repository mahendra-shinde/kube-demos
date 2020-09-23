# POD

- Wrapper for Containers
- May contain ONE or MORE containers
- Containers inside POD share network, host & volumes
- Two Containers CANNOT be listening on SAME PORT!

## Used as Part of 
- ReplicaSets:	 Stateless Pods in single group, scalable and self-healing.
- StatefulSets:	 Stateful Pods in single group, but have ordered creation and static-ips
- DaemonSets:	 System-pods running on EACH node.
- Jobs:			 Pods running single TASK, stops after task completes. Used for Batch Processing
- CronJobs:		 Jobs with Scheduling option. Recurring Jobs 	

## Pod Demo

