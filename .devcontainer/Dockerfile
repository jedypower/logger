ARG VARIANT=1.15.8
FROM docker.io/golang:$VARIANT

RUN groupadd --gid 1000 code \
  && useradd --uid 1000 --gid code --shell /bin/bash --create-home code

COPY .bash_prompt  /home/code/
RUN echo "Add shell customization" \
    && echo '. /home/code/.bash_prompt' >> '/home/code/.bashrc'

RUN apt-get update && \
    apt-get install --no-install-recommends -y \
        git \
        curl \
        gawk \
    && echo "Install Finished"

USER code

