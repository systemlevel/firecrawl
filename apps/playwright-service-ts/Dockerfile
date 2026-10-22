FROM node:22.23.4-bookworm-slim

WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install

COPY . .

ENV PLAYWRIGHT_BROWSERS_PATH=/usr/local/share/playwright

# Install Playwright dependencies
RUN npx playwright install chromium --with-deps

RUN npm run build

ARG PORT
ENV PORT=${PORT}

EXPOSE ${PORT}

CMD [ "npm", "start" ]
