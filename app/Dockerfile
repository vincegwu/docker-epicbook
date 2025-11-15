# Stage 1: Build
FROM node:18-alpine AS builder
WORKDIR /app
COPY . .
RUN npm ci

# Stage 2: Runtime
FROM node:18-alpine
WORKDIR /app
COPY --from=builder /app .
EXPOSE 8080
CMD ["node", "server.js"]