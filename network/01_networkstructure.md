## 네트워크의 구조

- 규모
  회사나 학교 등의 집단 크기에 따라 구분 - 사용자, 대역폭
- 업종
  공공기관, 제조, 금융, 게임 등의 업종에 따른 서비스 중요도
- 통신 방식과 경로
  Server&Client, Peer to Peer
- 토폴로지
  star, ring, mesh, bus, tree, redundancy

### 홈 네트워크

- 인터넷 - ISP - 모뎀 - 공유기 - 컴퓨터

### 기업용 네트워크

- ISP - 전용선 - 라우터 - 방화벽 - L3 백본 - L2 스위치 - 서버, 컴퓨터
  											  \- L4 로드밸런서 - DMZ

### 클라우드 네트워크 - AWS 기준

- 인터넷 - Route53 - IGW - VPC - ELB - Auto Scaling
  												\- Security Group - EC2