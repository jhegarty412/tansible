# Using AWX to provision SMG hosts

Login to [AWX](https://smg-awx.techservices.illinois.edu) using your AD credentials.

On the left hand side click the [Templates](https://smg-awx.techservices.illinois.edu/#/templates)

The first two templates are used to define services and hosts.

## Service creation
If you need to create a service tap the rocket icon next to the "0 Create Service" template.
It will then ask you to fill in the name of the new service along with the group cohorts for each
system class. Click NEXT and then LAUNCH to run the create service job.

## Host creation
After the service has been created new hosts may be defined with the '1 Create Host" template. 
Fill in the fields for the service, hostname, and hardware for the new host. Click NEXT and then LAUNCH 
run the create host job. At this point SMG will be notified to approve the new host. Once this approval
has happened you will receive an email automatically from AWX.

## Host provisioning
Once the service and host have both been defined there will be templates in tower for the service that will
allow provisioning the related host. Access to these jobs are granted based on AD groups that are
created from the grouper grouper. This process takes approximately 15 minutes after the service and host
approvals happen.

The templates are named "Provision Job SERVICE-NAME SYSTEM-CLASS" and "Deprovision Job SERVICE-NAME SYSTEM-CLASS".
Launch the appropriate template for the service and system class for the host you wish to create. It will prompt for 
a limit which is the hostname to be created. Click NEXT and LAUNCH. When the job is done running the host will be 
created and you can login via ssh using your AD credentials.
