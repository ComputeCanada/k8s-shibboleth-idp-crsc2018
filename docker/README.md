See https://github.com/Unicon/shibboleth-idp-dockerized for instructions about usage
of the image that the Compute Canada IdP Docker image is based on.

Once you have IdP configuration created and the Unicon image built on your machine the
Compute Canada image can be built using it as as base.

To build the Unicon base image clone their git repo and checkout the branch of the
version of the IdP version you are building. In this example we are checking out the
3.3.3 branch and building an image tagged with 3.3.3. In the shibboleth-idp-dockerized
cloned repo directory.

```bash
git checkout 3.3.3
docker build -t unicon/shibboleth-idp:3.3.3
```
