FROM node:16-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
RUN npm run build

FROM node:16-alpine AS backend
RUN npm install pm2 -g && npm i --omit=dev
COPY --from=builder /app/dist ./dist
