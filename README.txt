To deploy this on CloudBees, follow those steps:

Create database:
	bees db:create -u DB_USER -p DB_PASSWORD DBNAME

Change in src/main/resources/props/default.props:
(DB_HOST can be found on the cloudbees webpage for your database as "server:")

	# CloudBees MySQL Database
	db.url=jdbc:mysql://DB_HOST/DBNAME
	db.driver=com.mysql.jdbc.Driver
	db.user=DB_USER
	db.pass=DB_PASSWORD

Create a new maven project in Jenkins, changing the following:
	- Add your repository where your code with the above modifications is.
	- Also check "Deploy to CloudBees" with those parameters:
		CloudBees Site: USERNAME
		Application Id: USERNAME/APP_NAME
		Filename Pattern: target/*.war
