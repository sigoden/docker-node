# Node Minimal Docker Image

- base: node + npm
- slim: node only
- native: node + npm + c++ tools

## Usage

```
FROM sigoden/node:16-native
WORKDIR /app
COPY package.json package-lock.json ./
RUN npm ci --prod

# Only copy over the node pieces we need from the above image
FROM sigoden/node:16-slim
WORKDIR /app
COPY --from=0 /app .
COPY . .
EXPOSE 3000
CMD ["node", "index.js"]
```