# ============================================
# Stage 1: Node.js Build
# ============================================
FROM node:24-alpine AS builder
WORKDIR /app

# Vite 환경변수를 빌드 시점에 주입 (Jenkins에서 --build-arg로 전달)
ARG VITE_KAKAO_CLIENT_ID
ARG VITE_KAKAO_REDIRECT_URI
ARG VITE_API_BASE_URL

ENV VITE_KAKAO_CLIENT_ID=${VITE_KAKAO_CLIENT_ID}
ENV VITE_KAKAO_REDIRECT_URI=${VITE_KAKAO_REDIRECT_URI}
ENV VITE_API_BASE_URL=${VITE_API_BASE_URL}

COPY package*.json ./
RUN npm ci

COPY . .
RUN npm run build

# ============================================
# Stage 2: Nginx Serving
# ============================================
FROM nginx:stable-alpine

COPY --from=builder /app/dist /usr/share/nginx/html
COPY nginx/default.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
