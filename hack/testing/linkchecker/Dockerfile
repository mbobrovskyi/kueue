FROM python:3.16.0a1-alpine@sha256:53bdba10dcf8ada33490e83add833c0a31e74c71423ee0396f2e4f0de01b6148

RUN pip install --no-cache-dir linkchecker

COPY linkcheckerrc /etc/linkchecker/linkcheckerrc

ENTRYPOINT ["linkchecker", "--config=/etc/linkchecker/linkcheckerrc"]
