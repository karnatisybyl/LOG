FROM image-registry.openshift-image-registry.svc:5000/common-svc/wso2mi:4.2.0.41
ENV TZ=Africa/Nairobi
ARG MI_HOME=/home/wso2carbon/wso2mi-4.2.0

COPY bin/ ${MI_HOME}/bin
COPY security/ ${MI_HOME}/repository/resources/security
COPY dropins/	${MI_HOME}/dropins 
COPY lib/	${MI_HOME}/lib 
COPY conf/ ${MI_HOME}/conf
COPY cipher-config/ ${MI_HOME}/conf/security/
COPY repository/deployment/server/carbonapps/ ${MI_HOME}/repository/deployment/server/carbonapps

USER root
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone