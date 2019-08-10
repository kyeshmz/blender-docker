FROM ubuntu:xenial

LABEL authors="kkshmz <kyeshimizu@gmail.com> forked from Isaac (Ike) Arias <ikester@gmail.com>, "

RUN apt-get update && \
	apt-get install -y \
		curl \
		bzip2 \
		libfreetype6 \
		libgl1-mesa-dev \
		libglu1-mesa \
		libxi6 \
		libxrender1 
      blender && \
	apt-get -y autoremove && \
	rm -rf /var/lib/apt/lists/*
   
VOLUME /media
ENTRYPOINT ["/usr/local/blender/blender", "-b"]