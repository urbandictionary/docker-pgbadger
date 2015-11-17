[![Docker Repository on Quay](https://quay.io/repository/apeckham/pgbadger/status "Docker Repository on Quay")](https://quay.io/repository/apeckham/pgbadger)

Docker image to download RDS logs, run pgbadger, and upload the report to S3.

# To enable logging on RDS
```aws rds modify-db-parameter-group --db-parameter-group-name postgres-custom --parameters "ParameterName=log_min_duration_statement, ParameterValue=0, ApplyMethod=immediate"```

# To run
```docker run -e AWS_SECRET_ACCESS_KEY=XXX -e AWS_ACCESS_KEY_ID=YYY -e AWS_DEFAULT_REGION=ZZZ -e BUCKET=foobar -e DB_INSTANCE_IDENTIFIER=mydb -e LOG_FILE_COUNT=5 -v /mnt:/run quay.io/apeckham/pgbadger```