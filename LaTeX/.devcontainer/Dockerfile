FROM texlive/texlive:latest

#From https://gist.github.com/MichalZalecki/4a87880bbe7a3a5428b5aebebaa5cd97
ARG USER_NAME="main"
ARG USER_PASSWORD="main"

ENV USER_NAME $USER_NAME
ENV USER_PASSWORD $USER_PASSWORD
ENV CONTAINER_IMAGE_VER=v1.0.0

RUN echo $USER_NAME
RUN echo $USER_PASSWORD
RUN echo $CONTAINER_IMAGE_VER

# install the tooks i wish to use
RUN apt-get update && \
  apt-get install -y sudo \
  vim \
  less \
  curl \
  git-core \
  locales \
  procps \
  ssh \
  zsh \
  wget \
  # set up locale
  && locale-gen en_US.UTF-8 \
  && useradd -m -s /bin/zsh -G sudo $USER_NAME \
  && echo "${USER_NAME}:${USER_PASSWORD}" | chpasswd  
  
# the user we're applying this too (otherwise it most likely install for root)
USER $USER_NAME
# terminal colors with xterm
ENV TERM xterm
# set the zsh theme
ENV ZSH_THEME robbyrussell

# run the installation script  
#  RUN wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh || true
RUN sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"


# start zsh
CMD [ "zsh" ]
