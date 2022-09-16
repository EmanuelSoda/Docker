# Image for Single Cell Analysis analysis
##############################################–
## Start jupyter/datascience-notebook
FROM jupyter/datascience-notebook:ubuntu-22.04
## Change as u want
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


RUN mamba install --yes -c conda-forge \
  'openjdk' \
  'jaxlib' \
  'jax' \
  'scanpy' \
  'python-igraph' \ 
  #'scvi-tools'    \
  'leidenalg'  && \
  mamba clean --all -f -y && \
  fix-permissions "${CONDA_DIR}" && \
  fix-permissions "/home/${NB_USER}"

# --quiet 
RUN mamba install --yes -c bioconda \ 
  'bbknn' && \
  mamba clean --all -f -y && \
  fix-permissions "${CONDA_DIR}" && \
  fix-permissions "/home/${NB_USER}"

## Default command to initialize the container
CMD [ "bash" ]
############################################
