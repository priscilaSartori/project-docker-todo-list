FROM node:14-alpine
WORKDIR /frontend
EXPOSE 3000
ADD node_modules.tar.gz .
COPY ./ . 
CMD ["npm", "start"]

