FROM gbecedillas/pyalgotrade:0.17
MAINTAINER Gabriel Martin Becedillas Ruiz <gabriel.becedillas@gmail.com>

RUN pip install nose
RUN pip install coveralls

RUN mkdir /tmp/pyalgotrade

# Files needed to execute testcases.
COPY travis/run_tests.sh /tmp/pyalgotrade/
COPY coverage.cfg /tmp/pyalgotrade/
COPY setup.cfg /tmp/pyalgotrade/
COPY testcases /tmp/pyalgotrade/testcases
COPY samples /tmp/pyalgotrade/samples

# We need to upgrade the installed version with the one checked out from GIT.
COPY setup.py /tmp/pyalgotrade/
COPY pyalgotrade /tmp/pyalgotrade/pyalgotrade
RUN pip install -U /tmp/pyalgotrade
