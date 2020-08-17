FROM ubuntu:bionic
MAINTAINER nicolas_spalinger@sil.org

# See http://docs.docker.com/engine/articles/dockerfile_best-practices/

ENV LANG=C.UTF-8

USER root

WORKDIR /smith

# Configure the container, clean up some unneeeded packages,install smith and dependencies
RUN export DEBIAN_FRONTEND=noninteractive; \
    export DEBCONF_NONINTERACTIVE_SEEN=true; \
    echo 'tzdata tzdata/Areas select Etc' | debconf-set-selections; \
    echo 'tzdata tzdata/Zones/Etc select UTC' | debconf-set-selections; \
    apt-get update -qy \
 && apt-get install -qy --no-install-recommends tzdata software-properties-common \
 && apt-get clean \
 && add-apt-repository -sy ppa:silnrsi/smith-py3 \
 && add-apt-repository -sy ppa:fontforge/fontforge \
 && add-apt-repository -y ppa:jonathonf/texlive-2019 \
 && add-apt-repository -y ppa:git-core/ppa \
 && add-apt-repository -y ppa:sile-typesetter/sile \
 && apt-get remove *php* *mono* *dotnet* -y \
 && apt-get autoremove -y && apt-get upgrade -qy \
 && apt-get install python3-pip python3-setuptools git -y \
 && pip3 install --upgrade git+https://github.com/googlefonts/fontbakery.git@master#egg=fontbakery \
 && apt-get install libjson-perl libtext-csv-perl libharfbuzz-bin -y \
 && apt-get install smith-font -y --no-install-recommends \
 && apt-get install wamerican wbritish -y \
 && sile -e 'installPackage("fontproof");os.exit()'


