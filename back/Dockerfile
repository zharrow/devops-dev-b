FROM node:22

WORKDIR /app

ARG DATABASE_URL
ARG JWT_SECRET
ARG BCRYPT_SALT_ROUNDS

ENV DATABASE_URL=${DATABASE_URL}
ENV JWT_SECRET=${JWT_SECRET}
ENV BCRYPT_SALT_ROUNDS=${BCRYPT_SALT_ROUNDS}


COPY package*.json ./
RUN npm install

COPY . .

RUN npx prisma generate
RUN npx prisma db push
# RUN npx prisma migrate dev

EXPOSE 3000

CMD ["npm", "start"]