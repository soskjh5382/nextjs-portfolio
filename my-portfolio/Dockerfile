FROM node:20-alpine

# 앱 작업 디렉토리 생성
WORKDIR /app

# package.json 복사 및 의존성 설치
COPY package*.json ./
RUN npm install

# 이 줄이 있으면 이미지를 만들 때 소스코드를 베껴서 컨테이너 안에 복사해버립니다.
# 그런데 volumes: .:/app 으로 로컬 코드를 덮어씌우려고 할 때,
# Docker가 복사된 파일로 이미지를 먼저 만들고,
# 그 위에 바인드 마운트를 덮어씌우려다가 충돌 또는 비동기화가 발생합니다.
# 특히 Windows에선 이게 자주 문제돼요.
# 전체 소스 복사
#COPY . .

# Next.js는 기본적으로 3000 포트 사용
EXPOSE 3000

# 개발 서버 실행 (개발용)
CMD ["npm", "run", "dev"]