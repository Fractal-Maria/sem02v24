FROM ubuntu:24.04
RUN apt-get update \
    && apt-get dist-upgrade -y \
    && apt-get autoremove -y \
    && apt-get autoclean -y \
&& apt-get install -y \
    sudo \
    nano \
    wget \
    curl \ 
    git
RUN useradd -G sudo -m -d /home/Moria -s /bin/bash -p "$(openssl passwd -1 321)" Moria
USER Moria
WORKDIR /home/Moria
RUN mkdir hacking \
    && cd hacking \
    && curl -SL https://raw.githubusercontent.com/uia-worker/is105misc/master/sem01v24/pawned.sh > pawned.sh \
    && chmod 764 pawned.sh \
    && cd ..
RUN git config --global user.email «marim16@uia.no» \
    && git config --global user.name «Maria Mo» \
    && git config --global url."https://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:@github.com/".insteadOf "https://github.com" \
 && mkdir -p github.com/Fractal-Maria/sem02v24
 USER root
 RUN curl -SL https://go.dev/dl/go1.21.6.linux-arm64.tar.gz \
     | tar xvz -C /usr/local
 USER Moria
 SHELL ["/bin/bash", "-c"]
 RUN mkdir -p $HOME/go/{src,bin}
 ENV GOPATH="/home/Moria/go"
 ENV PATH="${PATH}:${GOPATH}/bin:/usr/local/go/bin"