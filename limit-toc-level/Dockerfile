FROM python:3.13.5-slim-bookworm

RUN apt update && apt upgrade -y

RUN pip install mkdocs

ARG USER_ID=1000
ARG GROUP_ID=${USER_ID}

RUN groupadd -g ${GROUP_ID} mkdocs \
  && useradd -u ${USER_ID} -g ${GROUP_ID} -m mkdocs

USER mkdocs
WORKDIR /home/mkdocs

RUN mkdir docs

ENTRYPOINT ["mkdocs"]
CMD ["serve", "--dev-addr=0.0.0.0:8000"]
