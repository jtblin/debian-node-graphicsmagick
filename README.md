# debian-node-graphicsmagick

Docker image based off `debian:stretch` with node `v4.4.3` and GraphicsMagick `1.3.23` installed.
This image is useful for front-end CI builds where one needs to compare screenshots with `gm` 
for example.

## Usage

Use as base image for your build:

```
FROM jtblin/debian-node-graphicsmagick
WORKDIR /src
ADD . ./
RUN chown -R node:node /src
USER node
RUN npm install && npm install bower && ./node_modules/bower/bin/bower install
CMD ["npm", "test"]
```

## License 

debian-node-graphicsmagick is copyright 2016 Jerome Touffe-Blin and contributors. 
It is licensed under the BSD license. See the include LICENSE file for details.