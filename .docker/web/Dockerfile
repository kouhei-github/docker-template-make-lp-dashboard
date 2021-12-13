FROM node:14.15-alpine

RUN apk update
RUN apk add git
RUN apk add --no-cache curl
RUN curl -o- -L https://yarnpkg.com/install.sh | sh
RUN yarn add @vue/cli
RUN yarn add @vue/cli-service-global
RUN yarn add @nuxtjs/composition-api
RUN yarn add create-nuxt-app

ENV TZ Asia/Tokyo
ENV PATH $HOME/.yarn/bin:$HOME/.config/yarn/global/node_modules/.bin:$PATH

WORKDIR /app

CMD ["/bin/ash"]