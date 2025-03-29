FROM ubuntu:24.04
LABEL version="1.0.0"

WORKDIR /ws
EXPOSE 8000

RUN apt update && apt upgrade -y && apt install -y build-essential

# default oh-my-zsh env
RUN apt install -y vim zsh wget git
RUN chsh -s /bin/zsh && sh -c "$(wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"

# builder env
RUN apt install -y cmake gcc-arm-none-eabi libnewlib-arm-none-eabi python3

RUN git clone https://github.com/raspberrypi/pico-sdk.git && cd pico-sdk && git submodule update --init --recursive && cd ..
ENV PICO_SDK_PATH=/ws/pico-sdk
