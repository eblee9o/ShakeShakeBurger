# 멀티 클라우드를 활용한 글로벌 프랜차이즈 인프라 구축
<br>

![1차 프로젝트_이은빈_0001](https://github.com/user-attachments/assets/a6b07c8f-ce04-4fad-9856-bf4a92c0d38f)
<br>
전세계 11개국 이상에 매장이 분포되어있고, 정형화된 메뉴를 판매하며, 온라인 주문 및 배달 서비스 확대하고 있는 글로벌 프랜차이즈 기업을 위한 인프라 구축을 통하여 <br>
멀티 리전 사용 뿐만 아니라 대용량 데이터 처리, 정교한 보안 정책, 높은 가용성, 자유로운 확장성 등의 이슈에 대하여 경험해 볼 수 있었습니다. 
<br>
<h3>구성도</h3>

![1차 프로젝트_이은빈_0006](https://github.com/user-attachments/assets/26f5f4fb-9599-4ebf-bacc-2720bf1ca0c1)
<br>
1. 주요 AWS 서비스 <br>
   yaml을 기반으로 cloudFormation 배포를 통해 기본 인프라를 구성하였고, Global Accererlator를 이용하여 멀티 리전 간 접속이 가능하도록 하였습니다.<br>

2. 인프라 <br>
   사용자가 접속 시 인터넷게이트웨이를 먼저 거친 후 Public Web으로 접속, 로드밸런서를 통하여 Private 인스턴스로 접속하는 방식으로 사용자의 요청이 처리되는 경로를 명확히 이해하고 안전하고 확장 가능한 인프라를 구축하고자 하였습니다.<br>
   또한 사용자의 요청이 인터넷게이트웨이와 로드밸런서를 먼저 거치면서 로드밸런서가 트래픽을 효율적으로 분산하는 것을 확인하고자 하였습니다.<br>
    보안, 트래픽 제어 및 커스터마이징을 위한 Nat 인스턴스를 생성하였으며, Python Flask를 통하여 웹 애플리케이션을 구현하였습니다.<br>
   동일한 디자인의 웹페이지의 언어를 변경하여 배포 후 Global accererlator와 VPN을 통하여 리전이 변경될 때 웹페이지 또한 변경되어 접속되는 것을 확인하였습니다.<br>
   Auto Scaling을 이용하여 접속량이 증가할때 인스턴스를 자동으로 생성하도록하여 가용성을 증대시켰습니다.<br>
   
