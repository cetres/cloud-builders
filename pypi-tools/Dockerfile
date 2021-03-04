FROM python:3.8-alpine

RUN apk add --update-cache --virtual build-dependencies \
       gcc musl-dev cargo libffi-dev openssl-dev python3-dev \
    && pip install setuptools wheel twine yolk3k keyring keyrings.google-artifactregistry-auth \
	&& apk del build-dependencies

ENTRYPOINT ["python"]