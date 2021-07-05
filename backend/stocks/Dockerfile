FROM node:12

# Create app directory
WORKDIR /usr/src/app


ENV WEBPORT 80
ENV NAMESPACE default
ENV USERSAPIHOST arcadia-users.$NAMESPACE
ENV LOGINAPIHOST arcadia-login.$NAMESPACE
ENV CASHTAPIHOST arcadia-cash-transfer.$NAMESPACE
ENV STOCKTAPIHOST arcadia-stock-transfer.$NAMESPACE
ENV STOCKSAPIHOST arcadia-stocks.$NAMESPACE


# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./
RUN npm install
COPY . .
# If you are building your code for production
# RUN npm ci --only=production

# Bundle app source
COPY . .

EXPOSE 80
CMD ["sh","-c", "node index.js --webPort=$WEBPORT --usersApiHost=$USERSAPIHOST --loginApiHost=$LOGINAPIHOST --cashtApiHost=$CASHTAPIHOST --stocktApiHost=$STOCKTAPIHOST --stocksApiHost=$STOCKSAPIHOST"]
