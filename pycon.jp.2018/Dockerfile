FROM node:8-stretch
MAINTAINER Hisahiro Ohmura <hisa_x@init.tw>
ARG GIT_BRANCH="master"

RUN apt-get update && apt-get upgrade -y
RUN mkdir /app && git clone https://github.com/pyconjp/pycon.jp.2018.git /app
WORKDIR /app/pycon.jp.2018
RUN git checkout -f origin/$GIT_BRANCH
WORKDIR /app
RUN npm install
RUN npm run build

EXPOSE 4000

CMD ["npm", "run", "start"]
