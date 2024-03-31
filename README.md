This repo was for experimenting with MLflow for ML tracking. An archived library of flash was leveraged as a wrapper around the lightning framework. 

Benefit of flash, https://medium.com/pytorch/introducing-lightning-flash-the-fastest-way-to-get-started-with-deep-learning-202f196b3b98v

Reason for flash archival, https://lightning.ai/forums/t/why-has-flash-lightning-been-archived/4390


This whole effort was to incrementally experiment with tools in various parts of the MLOps process, MLflow being the specific tool in this case. The machine learning task was sentiment classification of IMDB movie data.

MLproject file is used to track a multi-step DL pipeline in MLflow, different entry points for each pipeline step are defined. Each pipeline step then uses the data that's been shared, as well as other input parameters, to execute a specific task. Both the main pipeline-level function and each step of the pipeline are tracked using the MLflow tracking server, which produces a parent run_id to track the main pipeline run and multiple MLflow nested runs to track each pipeline's step. 

# Running locally
Make sure docker is installed: https://docs.docker.com/engine/install/
Make sure conda is installed: https://docs.anaconda.com/free/miniconda/index.html

The server setup is based on: https://github.com/sachua/mlflow-docker-compose

## Instructions for server setup
   1. `cd mlflow_docker_setup`
   2. `bash start_mlflow.sh`
#### To stop
   `bash stop_mlflow.sh`

## From project root, set up conda virtual environment dl_model by running:
   1. `conda env create -f conda.yaml`
   2. `conda activate dl_model`
   3. `python main.py`
   4. See the MLflow server UI at `http://localhost`
   5. See the object store (minIO, a multi-cloud object store) UI at `http://localhost:9000`



