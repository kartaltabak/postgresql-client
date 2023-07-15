FROM alpine

ARG USERNAME=postgres
ARG HOME_DIR=/home/$USERNAME

RUN adduser ${USERNAME} -D -h ${HOME_DIR}

RUN apk --no-cache add postgresql-client

USER ${USERNAME}

WORKDIR ${HOME_DIR}

