FROM alpine

RUN apk add --update nodejs npm

WORKDIR /client

COPY package*.json .

RUN npm install

COPY . . 

EXPOSE 3000

CMD ["npm","start"]