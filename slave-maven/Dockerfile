FROM registry.access.redhat.com/openshift3/jenkins-slave-maven-rhel7

MAINTAINER Ben Parees <bparees@redhat.com>

LABEL com.redhat.component="jenkins-skopeo-slave" \
      name="jenkins-skopeo-slave" \
      architecture="x86_64" \
      io.k8s.display-name="Jenkins Skopeo Slave Image Management" \
      io.k8s.description="Image management tools on top of the jenkins slave base image" \
      io.openshift.tags="openshift,jenkins,slave,copy"
USER root

RUN yum repolist > /dev/null && \
    yum clean all && \
    INSTALL_PKGS="skopeo" && \
    yum install -y --enablerepo=rhel-7-server-extras-rpms --setopt=tsflags=nodocs $INSTALL_PKGS && \
    rpm -V $INSTALL_PKGS && \
    yum clean all

USER 1001
