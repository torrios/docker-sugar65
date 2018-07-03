# README #

### What is this repository for? ###

SugarDockerized's ill-behaved cousin. Provides a Docker DEV environment for SugarCRM 6.5.x instances.
The repo provides an Apache 2.2 with PHP 5.3 container and a MySQL 5.5 container which satisfies the
support matrix for version 6.5.x at:

http://support.sugarcrm.com/Resources/Supported_Platforms/Sugar_6.5.x_Supported_Platforms/
 

## How do I get set up? ##

### PreRequisites ###

* Install Docker

### Setup ###

* Clone the repo
* Extract Sugar install or existing Sugar instance into the *www/sugar* folder
* If moving an existing instance then make sure to update config settings in *www/sugar/config.php*

## Usage ##

Starting the environment involves issuing the following command

```

docker-compose up --build -d

```

which will start the containers in the background. 

### Contribution guidelines ###

Well, this will probably never see the light of
day and so probably no one will contribute here.

### Who do I talk to? ###

* That would be me...Hector Rios
