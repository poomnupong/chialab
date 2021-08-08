FROM ubuntu:20.04

ENV TZ="America/Chicago"

RUN DEBIAN_FRONTEND=noninteractive apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y libsodium-dev tzdata

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN dpkg-reconfigure -f noninteractive tzdata

ENV PATH=/chia-mmplot/:$PATH
WORKDIR /chia-mmplot
ADD ./chia_plot chia_plot

#ENTRYPOINT ["bash", "./entrypoint.sh"]
