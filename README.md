Orchestrate Cohere LLMs with Apache Airflow
===========================================

This repository contains the DAG code used in the [Orchestrate Cohere LLMs with Apache Airflow tutorial](https://docs.astronomer.io/learn/airflow-cohere). 

The DAG in this repository uses the following packages:

- [Cohere Airflow provider](https://airflow.apache.org/docs/apache-airflow-providers-cohere/stable/index.html).
- [scikit-learn](https://scikit-learn.org/stable/).
- [pandas](https://pandas.pydata.org/).
- [numpy](https://numpy.org/).
- [matplotlib](https://matplotlib.org/).
- [seaborn](https://seaborn.pydata.org/).
- [adjustText](https://github.com/Phlya/adjustText).

# How to use this repository

This section explains how to run this repository with Airflow. Note that you will need to copy the contents of the `.env_example` file to a newly created `.env` file. You will need to have a Cohere account with a valid [Cohere API key](https://dashboard.cohere.com/api-keys) to run this repository. A free key is sufficient.

Download the [Astro CLI](https://docs.astronomer.io/astro/cli/install-cli) to run Airflow locally in Docker. `astro` is the only package you will need to install locally.

1. Run `git clone https://github.com/astronomer/airflow-cohere-tutorial.git` on your computer to create a local clone of this repository.
2. Install the Astro CLI by following the steps in the [Astro CLI documentation](https://docs.astronomer.io/astro/cli/install-cli). Docker Desktop/Docker Engine is a prerequisite, but you don't need in-depth Docker knowledge to run Airflow with the Astro CLI.
3. Create a `.env` file in the root of your cloned repository and copy the contents of the `.env_example` file to it. Provide your own Cohere API key in the `.env` file.
4. Run `astro dev start` in your cloned repository.
5. After your Astro project has started. View the Airflow UI at `localhost:8080`.
6. Run the `recipe_suggestions` DAG manually by clicking the play button. Provide your own pantry ingredients and adjust the parameters in the DAG to your liking.
7. You will find the recipes and the embedding similarity plot in the `include` folder.

In this project `astro dev start` spins up 4 Docker containers:

- The Airflow webserver, which runs the Airflow UI and can be accessed at `https://localhost:8080/`.
- The Airflow scheduler, which is responsible for monitoring and triggering tasks.
- The Airflow triggerer, which is an Airflow component used to run deferrable operators.
- The Airflow metadata database, which is a Postgres database that runs on port 5432.

## Resources

- [Orchestrate Cohere LLMs with Apache Airflow](https://docs.astronomer.io/learn/airflow-cohere).
- [Cohere Airflow provider documentation](https://airflow.apache.org/docs/apache-airflow-providers-cohere/stable/index.html).
- [Cohere documentation](https://docs.cohere.com/docs).