FROM ubuntu:20.04

EXPOSE 5001

RUN apt-get update && apt-get install -y curl \
    && curl -sL https://deb.nodesource.com/setup_16.x | bash \
    && apt-get install -y nodejs

WORKDIR /usr/src/app

COPY . .

RUN npm install && npm run build

RUN npm install -g serve
    
CMD ["serve", "-s", "build", "-l", "5001"]  