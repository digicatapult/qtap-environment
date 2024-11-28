# Use an official Anaconda image as the base
FROM continuumio/anaconda3

# Set working directory in the container
WORKDIR /app

# Install necessary OS-level dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    g++ \
    gcc \
    libopenblas-dev \
    libomp-dev \
    && rm -rf /var/lib/apt/lists/*

# Copy your project files and environment setup
COPY . /app

# Create the first environment (my_env1)
RUN conda env create -f /app/environment_env1.yml

# Create the second environment (my_env2)
# RUN conda env create -f /app/environment_env2.yml

# Set the default environment in the container
ENV CONDA_DEFAULT_ENV=my_env1
ENV PATH /opt/conda/envs/${CONDA_DEFAULT_ENV}/bin:$PATH

# Activate the environment
RUN echo "conda activate ${CONDA_DEFAULT_ENV}" >> /root/.bashrc

# Expose port 8888 to run Jupyter Notebook
EXPOSE 8888

# Configure the Jupyter Notebook server
RUN jupyter notebook --generate-config
RUN echo "c.NotebookApp.ip = '0.0.0.0'" >> /root/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.allow_root = True" >> /root/.jupyter/jupyter_notebook_config.py

# Start Jupyter Notebook
CMD ["jupyter", "notebook", "--no-browser", "--ip=0.0.0.0", "--port=8888", "--allow-root"] 