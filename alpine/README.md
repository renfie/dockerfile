docker build . -t eigen
docker run -d -p 8066:80 --name eigen-container eigen
