# spring-batch-demo

first job execution (powershell) - .\mvnw spring-boot:run "-Dspring-boot.run.jvmArguments=-Dspring.batch.job.name=downloadCsvFileJob" "-Dspring-boot.run.arguments=sourceFileUrl=https://raw.githubusercontent.com/lawlesst/vivo-sample-data/master/data/csv/people.csv targetFilePath=src/main/resources/data/people.csv"

second job execution (powershell) - .\mvnw spring-boot:run "-Dspring-boot.run.jvmArguments=-Dspring.batch.job.name=loadCsvToDatabaseJob" "-Dspring-boot.run.arguments=sourceFileUrl=https://raw.githubusercontent.com/lawlesst/vivo-sample-data/master/data/csv/people.csv targetFilePath=src/main/resources/data/people.csv"

# optional db with docker
docker run --name spring-batch-postgres -p 5432:5432 -e POSTGRES_USER=postgresql -e POSTGRES_PASSWORD=postgresql -e POSTGRES_DB=spring-batch-example -d postgres:13

If not running with docker, just create a new db connection named spring-batch, with an empty 'public' schema