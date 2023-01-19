# define the base image and JDK version
FROM jenkins/jenkins:lts-jdk11
WORKDIR /module6_task0
USER jenkins
# disable the Jenkins installation wizard
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false
# copy the plugins.txt file and run to install the plugins
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt
# Copy the groovy scripts to the container
CMD ["/sbin/tini", "--", "/usr/local/bin/jenkins.sh"]
