FROM maven:3-openjdk-16

#From https://gist.github.com/MichalZalecki/4a87880bbe7a3a5428b5aebebaa5cd97
ARG USER_NAME="main"
ARG USER_PASSWORD="main"

RUN echo $USER_NAME
RUN echo $USER_PASSWORD

# install the tooks i wish to use
USER root

# install the tooks i wish to use
RUN set -eux \
 && microdnf install curl \
  git-core \
  less \
  passwd \
  sudo \
  vim \
  wget \
  zsh \
  && microdnf clean all \
  # add a user (--disabled-password: the user won't be able to use the account until the password is set)
  && adduser -p ${USER_PASSWORD} --shell /bin/zsh --home /home/$USER_NAME -c "User" ${USER_NAME} \
  # update the password
  && echo ${USER_NAME}:${USER_PASSWORD} | chpasswd \
  && usermod -aG wheel ${USER_NAME}
  


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
