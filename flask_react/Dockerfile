FROM nikolaik/python-nodejs:python3.11-nodejs16-slim

WORKDIR /app

COPY . .

RUN pip config set global.index-url https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple && \
    pip install --upgrade pip && \
    pip install -r requirements.txt && \
    pip cache purge && \
    cd react_frontend && \
    npm config set registry https://registry.npmmirror.com/ && \
    npm install && \
    npm install -g serve && cd .. 

# Flask
CMD ["sh", "launch_app.sh"]
EXPOSE 5601 3000
