FROM node:18-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

# ✅ Embed your API URL at build time
ENV REACT_APP_API_URL=http://44.201.86.11:3001
ENV NODE_OPTIONS=--openssl-legacy-provider

RUN npm run build

FROM node:18-alpine
WORKDIR /app
RUN npm install -g serve
COPY --from=builder /app/build ./build
EXPOSE 3000
CMD ["serve", "-s", "build", "-l", "3000"]