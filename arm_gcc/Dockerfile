FROM frolvlad/alpine-glibc

# Set up a tools dev directory
WORKDIR /home/dev

RUN apk add \
    bzip2-dev \
    tar \
    wget
RUN wget -q -O gcc.tar.bz2 https://developer.arm.com/-/media/Files/downloads/gnu-rm/8-2018q4/gcc-arm-none-eabi-8-2018-q4-major-linux.tar.bz2?revision=d830f9dd-cd4f-406d-8672-cca9210dd220?product=GNU%20Arm%20Embedded%20Toolchain,64-bit,,Linux,8-2018-q4-major \
    && tar xvf gcc.tar.bz2 \
    && mv /home/dev/gcc-arm-none-eabi-8-2018-q4-major /home/dev/gcc \ 
    && rm /home/dev/gcc.tar.bz2 \
    && rm -rf /home/dev/gcc/share/doc \
    && rm -rf /home/dev/gcc/share/gcc-arm-none-eabi/samples
ENV PATH="/home/dev/gcc/bin:${PATH}"

ENTRYPOINT ["arm-none-eabi-gcc"]
