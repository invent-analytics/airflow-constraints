# Airflow Constraints

## What?

Since Airflow has lots of dependencies, and installing it is a bit tricky; Airflow maintainers provide a “known-to-be-working” constraints file for each version they release.

We depend on these constraints when we install Airflow to our production, build, and development images.

Although these constraints files work mostly, there were times that we need to change some pinned versions in those files at the past.

This project is a fork of these constraint files that helps us to be more flexible when we need to change pinned versions. Instead of using the official Airflow constraint files, we use our own fork.

You can read [this excelent document](https://airflow.apache.org/docs/apache-airflow/stable/installation/installing-from-pypi.html?highlight=constraints#constraints-files) to learn more and to understand the concept of Python dependency constraints.

## How?

There is a folder in this repo for each Airflow version that we want to use. Within that folders, there are multiple constraint files for multiple Python versions.

You can use the raw URL of a constraint file with the Airflow and Python version you need. For example;

```
https://raw.githubusercontent.com/invent-analytics/airflow-constraints/main/2.3.4/constraints-3.8.txt
```

So, the naming is like;

```
https://raw.githubusercontent.com/invent-analytics/airflow-constraints/main/${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt
```

## What if Airflow Releases a New Version?

When there is a new Airflow version, and you want to use it, what you need to copy the new constraints file from Airflow's GitHub repo.

They currently upload these file under a new git tag for each version. For example, constraints files for `2.3.4` version is tagged as `constraints-2.3.4` within the Airflow's GitHub repository. You can see an example [here](https://github.com/apache/airflow/tree/constraints-2.3.4).
