FROM node:14

# Create app directory
WORKDIR /app
ADD . /app/

# global install & update
RUN npm i -g npm && npm i -g create-nuxt-app
RUN npm install

ENV HOST 0.0.0.0
EXPOSE 3333

# start command
CMD [ "npm", "run", "dev" ]
