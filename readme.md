# Project LDAP V3 with Python

+ github repository: `https://github.com/OpenIdentityPlatform/OpenDJ`

+ running as a container as follows:

```bash
export IMAGE_NAME=openidentityplatform/opendj
export CONTAINER_NAME=opendj
export CONTAINER_HOSTNAME=ldap01.domain.com
export BASE_DN=dc=inflinx,dc=com

# Pull latest container
docker pull $IMAGE_NAME

# Start container
docker run -h $CONTAINER_HOSTNAME -p 1389:1389 -p 1636:1636 -p 4444:4444 \
-e BASE_DN=$BASE_DN --name $CONTAINER_NAME -t $IMAGE_NAME

# docker run -h ldap-01.domain.com -p 1389:1389 -p 1636:1636 -p 4444:4444 \
# --name ldap-01 openidentityplatform/opendj

docker logs --follow $CONTAINER_NAME

```

+ use apacheds studio tools located here: 
`https://directory.apache.org/studio/downloads.html`

+ importing ldap3: 
`pip3 install ldap3`

 website for python ldap3: 
`https://ldap3.readthedocs.io/en/latest/index.html`

+ ldif files extracted from: 
`https://github.com/apress/practical-spring-ldap`

+ test ldif files: 
`employees.ldif` and `patrons.ldif`


+ import ldif files into the ldap server using `import` feature of apacheds studio.
the second import should be an update since it is uses the same `dc=inflinx,dc=com`

+ when use `ldap3` library, make sure not to have spaces between the `dc`s
