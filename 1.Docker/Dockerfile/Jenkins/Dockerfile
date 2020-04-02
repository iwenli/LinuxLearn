FROM jenkins/jenkins:lts
USER root
WORKDIR /dotnet

# 维护者信息
LABEL description="集成NetCore3.1 SDK的jenkins" by="iwenli" maintainer="github.com/iwenli"

# RUN wget -O dotnet.tar.gz https://download.visualstudio.microsoft.com/download/pr/72ce4d40-9063-4a2e-a962-0bf2574f75d1/5463bb92cff4f9c76935838d1efbc757/dotnet-sdk-3.0.100-preview6-012264-linux-x64.tar.gz
RUN wget -O dotnet.tar.gz https://download.visualstudio.microsoft.com/download/pr/4acde034-669e-4d98-86ac-6214ebb36ff9/7e3cf7e4c323840c49ad7c3e4e2c7755/dotnet-sdk-3.1.103-linux-x64.tar.gz
RUN tar zxf dotnet.tar.gz -C ./
RUN rm -rf dotnet.tar.gz

ENV PATH="${PATH}:/dotnet:/var/jenkins_home/.dotnet/tools"
ENV DOTNET_ROOT="/dotnet"

RUN apt update -y
RUN apt install icu-devtools vim zip unzip -y

RUN usermod -a -G root jenkins
USER jenkins