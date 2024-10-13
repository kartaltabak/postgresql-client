FROM alpine

ARG USERNAME=postgres
ARG HOME_DIR=/home/$USERNAME

RUN adduser ${USERNAME} -D -h ${HOME_DIR}

RUN apk --no-cache add postgresql-client

ARG KTVERSION_FILE="/sbin/ktversion"

RUN echo "#!/usr/bin/env sh" > $KTVERSION_FILE && \
    echo -n "echo " >> $KTVERSION_FILE && \
    echo "$(psql --version | awk '{ print $3 }')" >> $KTVERSION_FILE && \
    chmod +x $KTVERSION_FILE

USER ${USERNAME}

WORKDIR ${HOME_DIR}

