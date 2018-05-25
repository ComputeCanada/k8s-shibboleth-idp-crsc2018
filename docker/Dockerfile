FROM unicon/shibboleth-idp:3.3.3

MAINTAINER Darren Boss <darren.boss@computecanada.ca>

#Add CC logo to webapp
ADD shibboleth-idp/ /opt/shibboleth-idp/
#Add http-forwarded to the list of modules for Jetty
ADD shib-jetty-base/ /opt/shib-jetty-base/
#Disallow /
ADD robots.txt /opt/shib-jetty-base/webapps/ROOT/robots.txt
#Blank index page for Jetty
ADD index.html /opt/shib-jetty-base/webapps/ROOT/index.html

RUN mkdir /opt/idp-conf \
    && cd /opt/idp-conf \
    && touch attribute-filter.xml cas-protocol.xml idp.properties ldap.properties metadata-providers.xml relying-party.xml saml-nameid.xml \
    && cd /opt/shibboleth-idp/conf \
    && rm attribute-filter.xml attribute-resolver.xml  cas-protocol.xml  idp.properties  ldap.properties  metadata-providers.xml  relying-party.xml  saml-nameid.xml \
    && ln -s /opt/idp-conf/attribute-filter.xml attribute-filter.xml \
    && ln -s /opt/idp-conf/attribute-resolver.xml attribute-resolver.xml \
    && ln -s /opt/idp-conf/cas-protocol.xml cas-protocol.xml \
    && ln -s /opt/idp-conf/idp.properties idp.properties \
    && ln -s /opt/idp-conf/ldap.properties ldap.properties \
    && ln -s /opt/idp-conf/metadata-providers.xml metadata-providers.xml \
    && ln -s /opt/idp-conf/relying-party.xml relying-party.xml \
    && ln -s /opt/idp-conf/saml-nameid.xml saml-nameid.xml \
    && mkdir /opt/shibboleth-idp/fed-metadata
