FROM node:26-alpine AS build
WORKDIR /app
# Node 25+ no longer bundles Corepack, so install it before enabling pnpm.
RUN npm install --global corepack && corepack enable
COPY package.json pnpm-lock.yaml ./
RUN pnpm install --frozen-lockfile
COPY tsconfig.json tsconfig.build.json ./
COPY src/ ./src/
RUN pnpm build

FROM node:26-alpine AS runtime
WORKDIR /app
COPY --from=build /app/dist ./dist
COPY --from=build /app/node_modules ./node_modules
COPY package.json ./
ENV NODE_ENV=production
EXPOSE 3002
CMD ["node", "dist/server.js"]
