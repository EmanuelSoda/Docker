# Image for Single Cell Analysis analysis

## Start from the jupyter/datascience-notebook
FROM jupyter/datascience-notebook


LABEL mantainer = "Emanuel Soda <emanuelsoda@gmail.com>"

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Install pacakges for single cell 
USER ${NB_UID}
# RUN conda install --yes  -c conda-forge \
#   'pytorch' \
#   'scvi-tools' && \
#   mamba clean --all -f -y && \
#   fix-permissions "${CONDA_DIR}" && \
#   fix-permissions "/home/${NB_USER}"


# RUN mamba install --yes -c conda-forge \
#   'openjdk' \
#   'jaxlib' \
#   'jax' \
#   #'scanpy' \
#   'python-igraph' \ 
#   'scvi-tools'    \
#   'leidenalg'  && \
#   mamba clean --all -f -y && \
#   fix-permissions "${CONDA_DIR}" && \
#   fix-permissions "/home/${NB_USER}"


# # --quiet 
# RUN mamba install --yes -c bioconda \ 
#   'bbknn' && \
#   mamba clean --all -f -y && \
#   fix-permissions "${CONDA_DIR}" && \
#   fix-permissions "/home/${NB_USER}"

RUN mkdir "/home/${NB_USER}/requirements"

COPY requirements.txt "/home/${NB_USER}/requirements"

RUN /opt/conda/bin/pip install -r /home/${NB_USER}/requirements/requirements.txt

## Default command to initialize the container
CMD [ "bash" ]
############################################
