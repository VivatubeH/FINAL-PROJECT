// 실습은 docker desktop을 다운받고 실행한 후, cmd 창에서 진행했다.

// 도커 이미지 다운로드
- docker pull nginx:latest

// 컨테이너 실행
- docker run -d -name my-nginx -p 8081:80 nginx
- 여기서 -d는 백그라운드 실행, my-nginx는 이름, 8081은 내가 지정할 포트번호

// 컨테이너 종료
- docker stop my-nginx

// 컨테이너 삭제
- docker rm my-ngingx

// 이미지 삭제
- docker rmi my-nginx

// 이미지가 없을 때 컨테이너를 실행하면 알아서 다운받는다.
