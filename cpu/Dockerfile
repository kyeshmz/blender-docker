FROM ubuntu:xenial

LABEL authors="kkshmz <kyeshimizu@gmail.com> forked from Isaac (Ike) Arias <ikester@gmail.com>, "
RUN apt-get update
RUN apt-get install software-properties-common -y && apt-get update
RUN add-apt-repository ppa:thomas-schiex/blender -y
RUN apt-get update && \
	apt-get install -y \
		curl \
		bzip2 \
		libfreetype6 \
		libgl1-mesa-dev \
		libglu1-mesa \
		libxi6 \
		libxrender1 && \
	apt-get -y autoremove && \
	rm -rf /var/lib/apt/lists/*

ENV BLENDER_BZ2_URL https://mirror.clarkson.edu/blender/release/Blender2.80/blender-2.80-linux-glibc217-x86_64.tar.bz2
RUN mkdir /usr/local/blender && \
	curl -SL "$BLENDER_BZ2_URL" -o blender.tar.bz2 && \
	tar -jxvf blender.tar.bz2 -C /usr/local/blender --strip-components=1 && \
	rm blender.tar.bz2
ENV echo 'alias blender="/usr/local/blender/blender"' >> ~/.bashrc   
VOLUME /media
