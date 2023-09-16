FROM amazon/aws-cli:latest

ARG USER_NAME="main"
ARG USER_PASSWORD="main"

ENV USER_NAME $USER_NAME
ENV USER_PASSWORD $USER_PASSWORD
ENV CONTAINER_IMAGE_VER=v1.0.0

RUN echo $USER_NAME
RUN echo $USER_PASSWORD
RUN echo $CONTAINER_IMAGE_VER

USER root

RUN yum install -y \
  vim \
  curl \
  git-core \
  less \
  locales \
  sudo \
  wget \
  zsh
  # add a user (--disabled-password: the user won't be able to use the account until the password is set)

RUN adduser -p ${USER_PASSWORD} --shell /bin/zsh --home /home/$USER_NAME -c "User" ${USER_NAME} \
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
