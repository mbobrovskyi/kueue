FROM python:3.15.0rc1-alpine@sha256:4b4340819382ffdbc0d87233b441daf617eec784e43458f8f5cb4d5e3b7d1838

RUN pip install --no-cache-dir linkchecker

COPY linkcheckerrc /etc/linkchecker/linkcheckerrc

ENTRYPOINT ["linkchecker", "--config=/etc/linkchecker/linkcheckerrc"]
