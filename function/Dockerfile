FROM arachnysdocker/athenapdf

ADD https://github.com/alexellis/faas/releases/download/0.9.4/fwatchdog /usr/bin/

RUN chmod +x /usr/bin/fwatchdog

ENV fprocess="athenapdf - -S"

CMD ["/usr/bin/fwatchdog"]
