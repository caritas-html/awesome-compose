FROM node:20-alpine

# Install Android's SDK tools
RUN apk add --no-cache openjdk11
RUN wget https://dl.google.com/android/repository/commandlinetools-linux-6858069_latest.zip -O cmdline-tools.zip && \
    unzip cmdline-tools.zip -d /sdk && \
    rm cmdline-tools.zip

ENV ANDROID_SDK_ROOT=/sdk
ENV PATH="$PATH:/sdk/cmdline-tools/bin"

WORKDIR /app
COPY package.json ./
RUN npm install

COPY . .

CMD ["npm", "start"]