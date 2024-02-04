# --- builder ---
FROM node:18-alpine as builder

WORKDIR /app
COPY . .

# Be sure to add "dokku docker-options:add ridgetop build '--build-arg PUBLIC_POCKETBASE_URL=`dokku config:get ridgetop PUBLIC_POCKETBASE_URL`'"
ARG PUBLIC_POCKETBASE_URL=notthekey
ENV PUBLIC_POCKETBASE_URL ${PUBLIC_POCKETBASE_URL}
RUN echo $PUBLIC_POCKETBASE_URL

RUN npm ci
RUN npm run build

# --- runner
FROM node:18-alpine as runner

WORKDIR /srv

COPY --from=builder /app/build /srv/
COPY --from=builder /app/package*.json /srv/

RUN npm i --production

EXPOSE 5173
CMD node .