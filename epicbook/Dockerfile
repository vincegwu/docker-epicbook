FROM node:18-alpine AS builder
WORKDIR /epicbook
COPY . .
RUN npm install

FROM node:18-alpine AS runtime
WORKDIR /epicbook
COPY --from=builder /epicbook .
CMD ["node", "server.js"]