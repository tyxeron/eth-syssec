# Part 6: OS Security Introduction
- OS controls access to resources
- OS schedules processes
- OS offers security features to processes
- «Secure Operating System»
	- Provide security mechanisms
	- Ensures security goals are enforced
	- Even in presence of threats
- There is no such thing as a completely secure operating system
- Trusted/verified system have typically very limited functionality

## Access Control
- OS has to decide if requests from multiple subjects (e.g. users, processes) to perform operations (e.g. read, write, execute) on objects (e.g. socket, files) should be allowed or not
- Lampson's Access Matrix: a function  \\[ops(s, o) \subseteq \operatorname{OP} \\] determines which operation in the set  \\[\operatorname{OP} \\] a subject  \\[s \\] can do on an object  \\[o \\].
- Discretionary Access Control (DAC)
	- Access restriction to an object is based on the subject it belongs to.
	- Depending on the access permission of the subject it can pass its permissions to any other subject
	- Works well if processes and users are benign and make no mistakes (not realistic)
- Mandatory Access Control (MAC)
	- Can only be modified by trusted subjects (e.g. administrators) via a trusted software
	- Can be used alongside Discretionary Access Control
	- Subjects and objects represented by labels
	- Labels are tamperproof, can only be set by trusted subjects using trusted software
	- Labels are immutable during system execution
	- Labeling state: maps processes and system resources to labels
	- Transition state: allowed ways a process or resource can be relabled
- Reference Monitor
	- Request to perform security-sensitive operation as input
	- Binary output indicating if the request can be authorized by the policy
	- Contains Policy Store: database containing protection state, labeling state and transition state
	- Complete mediation: all security-sensitive operations must be mediated
	- Tamperproof: not possible to modify or disable by unauthorised subjects
	- Verifiable: small enough to be analysed
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0OTEyNzkxMDddfQ==
-->