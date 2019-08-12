FROM nvidia/cuda:10.0-cudnn7-devel-ubuntu18.04
LABEL maintainer="kkshmz"

ENV LANG=C.UTF-8 LC_ALL=C.UTF-8

RUN apt-get update --fix-missing && \
    apt-get install -y --no-install-recommends wget bzip2 ca-certificates libglib2.0-0 libfreetype6 libgl1-mesa-dev libglu1-mesa libxi6 libxext6 libsm6 libxrender1 git mercurial subversion unzip libjpeg-dev libpng-dev build-essential vim && \
    apt-get -y autoremove && apt-get -y autoclean

RUN rm -rf /var/cache/apt

#install anaconda and install pytorch
RUN wget --quiet https://repo.anaconda.com/archive/Anaconda3-2019.07-Linux-x86_64.sh -O ~/anaconda.sh && \
    /bin/bash ~/anaconda.sh -b -p /opt/conda && \
    rm ~/anaconda.sh && \
    ln -s /opt/conda/etc/profile.d/conda.sh /etc/profile.d/conda.sh && \
    echo ". /opt/conda/etc/profile.d/conda.sh" >> ~/.bashrc && \
    echo "conda activate base" >> ~/.bashrc && \
    find /opt/conda/ -follow -type f -name '*.a' -delete && \
    find /opt/conda/ -follow -type f -name '*.js.map' -delete && \
    /opt/conda/bin/conda clean -ya
#set conda env 
ENV PATH /opt/conda/bin:$PATH
#set command default


ENV BLENDER_BZ2_URL https://mirror.clarkson.edu/blender/release/Blender2.80/blender-2.80-linux-glibc217-x86_64.tar.bz2
RUN mkdir /usr/local/blender && \
	curl -SL "$BLENDER_BZ2_URL" -o blender.tar.bz2 && \
	tar -jxvf blender.tar.bz2 -C /usr/local/blender --strip-components=1 && \
	rm blender.tar.bz2
ENV echo 'alias blender="/usr/local/blender/blender"' >> ~/.bashrc   
CMD [ "/bin/bash" ]
