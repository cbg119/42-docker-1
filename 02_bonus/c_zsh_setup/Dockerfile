FROM ubuntu
RUN apt-get update -y && apt-get upgrade -y \
	&& apt-get install -y wget vim git zsh git

ADD https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh .

USER root

RUN chmod 777 install.sh && ./install.sh && rm install.sh \
	&& cd ~ && echo "alias 42_gcc='gcc -Wall -Wextra -Werror \$*'" >> .zshrc \
	&& mkdir /cadet

CMD cd /projects && zsh
