#
# This is the official OpenShift Origin image. It has as its entrypoint the OpenShift
# all-in-one binary.
#
# The standard name for this image is openshift/origin
#
FROM openshift/origin-base

RUN mkdir -p /var/lib/openshift

ADD bin/openshift        /usr/bin/openshift
RUN ln -s /usr/bin/openshift /usr/bin/osc && \
    ln -s /usr/bin/openshift /usr/bin/openshift-deploy && \
    ln -s /usr/bin/openshift /usr/bin/openshift-docker-build && \
    ln -s /usr/bin/openshift /usr/bin/openshift-sti-build && \
    ln -s /usr/bin/openshift /usr/bin/osadm && \
    ln -s /usr/bin/openshift /usr/bin/openshift-router

ENV HOME /root
ENV OPENSHIFTCONFIG /var/lib/openshift/openshift.local.config/master/admin.kubeconfig
WORKDIR /var/lib/openshift
ENTRYPOINT ["/usr/bin/openshift"]
