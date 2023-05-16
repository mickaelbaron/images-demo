ARG BASE_IMAGE=inseefrlab/onyxia-base
FROM $BASE_IMAGE

SHELL ["/bin/bash", "-c"]

ENV JAVA_HOME /usr/local/openjdk-17
ENV PATH $JAVA_HOME/bin:$PATH

# Default to UTF-8 file.encoding
ENV LANG C.UTF-8

USER root

RUN wget --progress=dot:giga -O openjdk.tgz https://download.java.net/java/GA/jdk17/0d483333a00540d886896bac774ff48b/35/GPL/openjdk-17_linux-x64_bin.tar.gz; \
    mkdir -p "$JAVA_HOME"; \
    tar --extract \
		--file openjdk.tgz \
		--directory "$JAVA_HOME" \
		--strip-components 1 \
		--no-same-owner \
	; \
    rm openjdk.tgz*

USER 1000

CMD ["jshell"]