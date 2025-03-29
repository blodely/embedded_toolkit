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

# pico-sdk env
RUN cd / && git clone --recurse-submodules https://github.com/raspberrypi/pico-sdk.git
ENV PICO_SDK_PATH=/pico-sdk

# picocalc env
RUN cd / && git clone --recurse-submodules https://github.com/clockworkpi/PicoCalc.git
