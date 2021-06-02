# Minimal Node.js Docker Images

- Full install built with npm and c++
- Full install built with npm
- Slim install with no npm

## Usage

```
FROM sigoden/node:14-native
WORKDIR /app
COPY package.json package-lock.json ./
RUN npm ci --prod

# Only copy over the node pieces we need from the above image
FROM sigoden/node:14-slim
WORKDIR /app
COPY --from=0 /app .
COPY . .
EXPOSE 3000
CMD ["node", "index.js"]
```