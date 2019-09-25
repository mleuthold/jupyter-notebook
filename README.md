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