#
# Dell EMC OpenManage Ansible Modules
# Copyright (C) 2020 Dell Inc. or its subsidiaries. All Rights Reserved.

# GNU General Public License v3.0+ (see COPYING or https://www.gnu.org/licenses/gpl-3.0.txt)
#

FROM python:3-slim

LABEL author="Saishiva K (@saishivarcr)"

ENV path /dellemc
RUN mkdir $path
WORKDIR $path

RUN pip install "ansible<2.10" omsdk

ADD https://github.com/dell/dellemc-openmanage-ansible-modules/archive/devel.tar.gz .

RUN tar -xvf devel.tar.gz && \
    cd dellemc-openmanage-ansible-modules-devel && \
    python install.py

VOLUME [$path]

ENTRYPOINT ["/usr/local/bin/ansible-playbook"]
