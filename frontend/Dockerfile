FROM node:18
WORKDIR /app

COPY package.json package.json
COPY package-lock.json package-lock.json

RUN npm install

COPY . .
RUN npm run build

# Копируем собранные файлы в /staticfiles для nginx
RUN mkdir -p /staticfiles && cp -r build/* /staticfiles/

# Запускаем простую команду, которая не занимает порт
CMD ["echo", "Frontend static files built and copied to /staticfiles"]