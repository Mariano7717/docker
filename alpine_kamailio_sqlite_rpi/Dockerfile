FROM armhf/alpine

MAINTAINER Alberto Sagredo <info@voipnovatos.es>

ENV build_date 2016-11-18

ENV DEBIAN_FRONTEND noninteractive

ENV SIP_PORT 5060

ENV TLS_PORT 5061

RUN apk add --no-cache sqlite kamailio kamailio-presence kamailio-tls bash joe python kamailio-debugger kamailio-dbg kamailio-xml kamailio-sqlite libssl1.0 

ADD conf/etc/* /etc/kamailio/

ADD boot_run.sh /etc/

WORKDIR /etc/kamailio/

RUN mkdir /etc/kamailio/certs

ADD conf/etc/certs/* /etc/kamailio/certs/

EXPOSE $SIP_PORT $SIP_PORT/udp $TLS_PORT

RUN chmod a+x /etc/boot_run.sh

ENTRYPOINT ["/etc/boot_run.sh"]
