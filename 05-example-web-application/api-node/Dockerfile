FROM node:19.6-alpine

WORKDIR /usr/src/app

ENV NODE_ENV=production

#RUN apt-get update && apt-get install -y nodejs npm

COPY package*.json ./

RUN --mount=type=cache,target=/ur/src/app/.npm \
    npm set cache /usr/src/app/.npm && \
    npm ci --only=production

USER node

COPY --chown=node:node ./src .

EXPOSE 3000

CMD ["node","index.js"]