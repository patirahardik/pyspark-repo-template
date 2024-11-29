FROM bitnami/spark:3.5.1 as spark-gateway

USER root

# Update package list and install git
RUN apt-get update && apt-get install -y git

WORKDIR /workspaces

# Copy requirements file and install Python dependencies
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

EXPOSE 8888


# Copy any local files into the container (optional)
WORKDIR /workspaces
COPY requirements.txt requirements.txt
RUN pip3 install  --force-reinstall -r requirements.txt

# Command to start PySpark with Jupyter
#CMD ["bash", "-c", "start-master.sh && start-worker.sh spark://$(hostname):7077 && pyspark"]
