To deploy this on CloudBees, follow those steps:

Create database:
	bees db:create -u DB_USER -p DB_PASSWORD DBNAME

Bind database as datasource:
	bees app:bind -db DBNAME -a MYAPP_ID -as LiftDB

Create a new maven project in Jenkins, changing the following:
	- Add your repository where your code with the above modifications is.
	- Also check "Deploy to CloudBees" with those parameters:
		CloudBees Site: USERNAME
		Application Id: USERNAME/APP_NAME
		Filename Pattern: target/*.war
