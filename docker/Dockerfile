FROM continuumio/miniconda3:latest 
####################################################################################################
# Base Development image
# Installs the requirements in setup.py for devs, full install of pytorch_fnet for GPU support 
# Mainly for development uses and running examples from Allen Cell Science:
# https://github.com/AllenCellModeling/pytorch_fnet
####################################################################################################
LABEL org.opencontainers.image.authors="Amil Khan, UCSB"


# Install vim for quick updates in the container
RUN apt update && apt install -y git vim 

WORKDIR workspace

# Clone the pytorch_fnet repo into /workspace
RUN git clone https://github.com/AllenCellModeling/pytorch_fnet.git

# Modified setup.py with necessary bug fixes
COPY setup.py pytorch_fnet


# Compile the pytorch_fnet repo, includes pip installs 
RUN pip install pytorch_fnet/[dev]
