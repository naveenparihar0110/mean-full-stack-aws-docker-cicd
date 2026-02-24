# Stage 1: Install dependencies
FROM node:18-alpine AS build

WORKDIR /app

COPY package*.json ./
RUN npm install --omit=dev

COPY . .

# Stage 2: Runtime image
FROM node:18-alpine

WORKDIR /app

COPY --from=build /app /app

EXPOSE 5000

CMD ["node", "server.js"]
