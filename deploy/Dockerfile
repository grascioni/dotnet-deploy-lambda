FROM mcr.microsoft.com/dotnet/sdk:6.0

LABEL "com.github.actions.name"="dotnet lambda deploy"
LABEL "com.github.actions.description"="Run dotnet lambda deploy"
LABEL "com.github.actions.icon"="play-circle"
LABEL "com.github.actions.color"="purple"

LABEL "repository"="https://github.com/grascioni/dotnet-deploy-lambda"
LABEL "homepage"="https://github.com/grascioni/dotnet-deploy-lambda"
LABEL "maintainer"="Gustavo Rascioni <gustavorascioni@gmail.com>"

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
      groff \
      jq \
      python \
      python3-pip \
      python3-setuptools \
      zip \
    && rm -rf /var/lib/apt/lists/* \
    && pip3 install awscli

RUN dotnet tool install -g Amazon.Lambda.Tools

COPY entrypoint.sh /entrypoint.sh

RUN chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]
