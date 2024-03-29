FROM jenkins/jenkins:2.277.1
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false -Dhudson.model.ParametersAction.keepUndefinedParameters=true
ENV CASC_JENKINS_CONFIG /var/jenkins_home/casc.yaml
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt
COPY jenkins_casc_vm.yaml /var/jenkins_home/casc.yaml
USER 0

# You need to fill in the following empty to setup the sever.

# Configurations related to Jenkins instance
ENV JENKINS_ADMIN_ID=admin \
    JENKINS_ADMIN_PASSWORD=admin \
    JENKINS_URL=http://localhost:8080/ \
    JENKINS_ADMIN_EMAIL_ADDRESS=admin@sample.org \
    SMTP_HOST= \
    SMTP_PORT= \
    SMTP_USERNAME= \
    SMTP_APP_PASSWORD= \
    EMAIL_NOTIFICATION_RECEIVERS=
    
# Configurations related to Micro Integrator instance in different environments
ENV DEV_ENVIRONMENT_IP= \
    DEV_MICRO_INTEGRATOR_CAPPS_PATH= \
    DEV_REMOTE_ROOT_USER=ubuntu \
    STAGING_ENVIRONMENT_IP= \
    STAGING_MICRO_INTEGRATOR_CAPPS_PATH= \
    STAGING_REMOTE_ROOT_USER= \
    PROD_ENVIRONMENT_IP= \
    PROD_MICRO_INTEGRATOR_CAPPS_PATH= \
    PROD_REMOTE_ROOT_USER=ubuntu \
    SYNAPSE_TEST_FRAMEWORK_CONFIGS='-DtestServerType=remote -DtestServerHost= -DtestServerPort='

# Configurations related to Nexus instance   
ENV NEXUS_VERSION=nexus3 \
    NEXUS_PROTOCOL=HTTP \
    NEXUS_URL= \
    NEXUS_USERNAME=adminuser \
    NEXUS_PASSWORD=admin123 

# Configurations related to source and deployment project in Github  
ENV GIT_SCM_CONFIG_USERNAME= \
    GIT_SCM_CONFIG_EMAIL= \
    GIT_SCM_CONFIG_PASSWORD_TOKEN= \
    GIT_SCM_PROJECT_ID=integration-project \
    SOURCE_GIT_RESPOSITORY= \
    DEPLOYMENT_GIT_RESPOSITORY= \
    DEPLOYMENT_DEV_BRANCH=dev \
    DEPLOYMENT_STAGING_BRANCH=staging \
    DEPLOYMENT_PROD_BRANCH=prod

# Configurations related to Integration project
ENV PROJECT_NAME= \
    PROJECT_GROUPID= \
    PROJECT_GROUPID_PATH= \
    PROJECT_CAPP_ARTIFACTID=