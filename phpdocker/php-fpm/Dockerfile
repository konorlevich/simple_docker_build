FROM phpdockerio/php73-fpm:latest
WORKDIR "/application"

# Fix debconf warnings upon build
ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get -y install apt-utils
# Install selected extensions and other stuff
RUN apt-get -y --no-install-recommends install  php-xdebug php7.3-intl php-yaml

# Install git
RUN apt-get -y install git

RUN apt-get -y install vim zsh \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN zsh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
RUN git clone https://github.com/shengyou/codeception-zsh-plugin.git /root/.oh-my-zsh/custom/plugins/codeception
RUN git clone https://gitlab.com/code-stats/code-stats-zsh.git /root/.oh-my-zsh/custom/plugins/codestats
COPY zshrc "/root/.zshrc"

RUN curl -fLo /root/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
COPY vimrc "/root/.vimrc"

SHELL ["zsh"]
