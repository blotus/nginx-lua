# pathwar/nginx-lua:1.7.11
FROM debian:jessie
MAINTAINER Pathwar Team <team@pathwar.net> (@pathwar_net)

# Install dependencies
RUN apt-get update
 && apt-get -y -q upgrade \
 && apt-get clean

# Add Pathwar tools
COPY skeleton /pathwar
COPY nginx-lua_1.7.11_amd64.deb /
RUN apt-get install libpcre3 libluajit-5.1-2 libssl1.0.0
RUN dpkg -i /nginx-lua_1.7.11_amd64.deb
RUN rm -f /nginx-lua_1.7.11_amd64.deb

EXPOSE 80 443
# Override pathwar scripts
RUN echo 'nginx -g "daemon off;"' > /pathwar/scripts/run
