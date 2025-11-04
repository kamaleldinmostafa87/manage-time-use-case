
# Manage Time use-case

## Vision: The employee wants to submit a new request for vacation time

## Actors:

■ Employee: An employee uses this system to manage his or her vacation time.
 ■ Manager: An employee who has all the abilities, goals of a regular employee
 ■ Clerk: A member of the HR department who has sufficient rights to view employees’ personal data 
 ■ System Admin: A role responsible for the smooth running of the system’s technical resources (e.g., Web server, database) and for collecting and archiving all log files

## Domain
- management vacation requests of employees
## Function Requirement: 

- login feature 
- create vacation request for employee and fill required fields for the request
- cancel / edit the request for the employee
- approve/reject availability for the vacation request from the manager
- send mail automatically from system to manager and from the manager to the employee

## Non-Function Requirement

- security:
	-  system uses the portal’s single-sign-on mechanisms for all authentication.
- performance : 
	- system should allow to the manager selects each of these one at a time to individually approve or deny
	
- scalability:
	- system must handle many requests which comes to the manager
	- system must implement a flexible rules-based system for validating and verifying leave time requests
	- system must enable the HR and system administration personnel to override all actions restricted by rules, with logging of those overrides

# Constrains

- The employee is identified as an employee of the company 
- The employee must have privileges to manage his or her own vacation time.
- four hours might indicate a half-day vacation time request
- The employee enters a short title and description (no more than a paragraph in length
- If the request is disapproved, the manager is required to enter an explanation


## Assumption

- The employee is authenticated by the portal frameworks
- The employee is identified as an employee of the company 
- The employee must have privileges to manage his or her own vacation time.
- The system initially had a capacity for 10,000 employees.
- The VTS uses outstanding balances and Information is displayed for the previous 6 months and up to 18 months in the future.

## Flow-Chart

![[Flowchart.svg]]



## Epsuedo code

	```
	 FUNCTION login (email, pass){
	IF valid data
		navigate to the main page
	}
	ELSE {
		display errors  
	}
	}

	FUNCTION createVacationRequest(){
	IF valid data 
		submit successfully
		then navigate to the main page
		mail sent successfully to the manager
		
		mailConfig(managerEmail)
	ELSE 
		display errors with wrong data		
	}



	FUNCTION sendEmailtoManager(){
		info data will display in the Email
		//approve or reject
			if(accept) send approved mail
			 if(reject) send rejection mail
			 then
			 return to the main page 
	}
	FUNCTION mailConfig(email) 
	 const subject = ""
	 send to manager  {email}
	```



## Sequence Diagram
![[_مخطط دون اسم_.drawio.svg]]