FROM node:22.11.0-slim

ENV LANG=C.UTF-8 \
    TZ=Asia/Tokyo

ARG UID
ARG GID
ARG USERNAME

# RUN groupadd -g ${GID} ${USERNAME} && useradd -m -s /bin/bash -u ${UID} -g ${GID} ${USERNAME}
# RUN groupadd -g ${GID} ${USERNAME} && useradd -m -s /bin/bash -u ${UID} -g ${GID} ${USERNAME} \
#     mkdir -p /app && chown -R ${USERNAME}:${USERNAME} /app

WORKDIR /app

COPY package.json package-lock.json ./

RUN npm install

COPY . .

EXPOSE 5173
# USER ${UID}:${GID}
USER node
CMD [ "npm","run","dev" ]