FROM node:9.11.1

WORKDIR /code

# Add dependencies
ADD ./package.json /code
ADD ./bower.json /code
ADD ./gulpfile.js /code
ADD ./.eslintrc /code
ADD ./karma.conf.js /code

# Install Prerequisites
RUN npm install -g bower gulp

RUN npm link gulp

RUN npm cache clean -f
RUN npm install
RUN bower install --allow-root

CMD ["gulp", "dev:runserver"]

EXPOSE 8888
