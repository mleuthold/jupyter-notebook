# Requirements

- `python3` is available
- `pip3` is available
- install build tool [Taskfile](https://taskfile.dev/#/installation?id=installation) or execute `curl -sL https://taskfile.dev/install.sh | sh` directly
- valid dummy _AWS credentials_ are available

# Usage

Note: Requirements (Python libraries) will be installed automatically

Execute Jupyter notebook with given ISIN
```shell script
ISIN=CA32076V1031 task run.notebook
```

Output is located in:
```shell script
output/result_set.csv
```

Temporary data will be downloaded to:
```shell script
data/*
```

# Documentation

Data exploration is located [here](docs/data exploration.html).

Application code is located [here](docs/app development.html).

# Limitations

Only data of September 2019 is processed. An issue with availability of AWS Credentials in PySpark forced me to work with data locally. Therefore just a sub-set is downloaded to the local machine. To not overwhelm my system, I decided to go for the current month only (state: 25th September 2019).

# Improvements
## Dependencies
Dockerizing the whole project would negate the need for handling all requirements mentioned above. However, due to time constraints and for just show casing a working product, this is a balanced trade-off.

## Testing
If this code would go to `production`, I would rewrite the code from a Jupyter notebook to a simple Python app. This would open the possibility to test the code with a framework like `PyTest`.

## Accessibility
If this code would face data consumers or other microservices, I would wrap the Python app into a Flask app. So with a call to an endpoint with a given ISIN a response is returned containing the desired result set.

## Latency
If latency is an issue, I would reorganize the data, i.e. instead of using files from a S3 bucket putting an Athena table on top of the CSV files, to do the SQL querying directly in AWS. 

Latency could be pushed down even further by using a database with a cache, but this requires additional effort like a pipeline/cron job fill the database regularly.