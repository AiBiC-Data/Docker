FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

#VOLUME ["/app/feedback"]      # 2 이후 추가 4까지 진행 했는데 볼륨을 명시하지 않아 실패 따라서 이렇게 하는 것이 아님

CMD ["node", "server.js"]

# 1. docker build -t feedback-node .
# 2. docker run -p 3000:80 -d --name feedback-app --rm feedback-node
# 3. revise server.js file -> docker build -t feedback-node:volume .
# 4. docker run -d -p 3000:80 --rm --name feedback-app feedback-node:volume
# 5. docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback feedback-node:volume 이렇게 하면 feedback이란 볼륨이 생성되고 실행이 잘 됨
# 6. Mount Binding -> docker run -d -p 3000:80 --name feedback-app -v feedback:app/feedback -v $(pwd):/app feedback-node:vloumes 이렇게 하면 충돌로 실행이 안됨
# 6. Mount Binding 새 볼륨추가-> docker run -d -p 3000:80 --name feedback-app -v feedback:app/feedback -v $(pwd):/app -v /app/node_modules feedback-node:vloumes