FROM debian:latest

LABEL "maintainer"="Uzair Akbar <uzairakbar025@gmail.com>"
LABEL "repository"="https://github.com/uzairakbar/ml-notes"
LABEL "homepage"="https://github.com/uzairakbar/ml-notes"

LABEL "com.github.actions.name"="Convert to PDF"
LABEL "com.github.actions.description"="Convert documents to PDF with xelatex."
LABEL "com.github.actions.icon"="code"
LABEL "com.github.actions.color"="blue"

ENV DEBIAN_FRONTEND noninteractive

# Install all TeX and LaTeX dependencies
RUN apt-get update && \
    apt-get install --yes --no-install-recommends \
    texlive-fonts-recommended \
    # texlive-generic-recommended \
    texlive-latex-recommended \
    texlive-lang-english \
    texlive-xetex && \
    apt-get autoclean && apt-get --purge --yes autoremove && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ADD entrypoint.sh /entrypoint.sh

RUN chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]