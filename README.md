# CKAN 설치
## CKAN 설치 방법들
- Install from an operating system package
- Install from source
- Install from Docker Compose
	- From OS package is the quickest and easiest way to install CKAN, but it requires Ubuntu 16.04 64-bit 64-bit. 
	- 정확히 Ubuntu 16.04 64-bit가 아니면 소스로부터 설치해야 함. 아래에 케이스가 해당됨
		- You want to install CKAN on a 32-bit computer, or
		- You want to install CKAN on a different version of Ubuntu, not 16.04, or
		- You want to install CKAN on another operating system (eg. RHEL, CentOS, OS X), or
		- You want to run multiple CKAN websites on the same server, or
		- You want to install CKAN for development
- ==그러므로 소스를 통한 설치를 전제함==

## 전제
- docker 설치
   > 설치 방법: https://ldccai.lotte.net/gitlab/bellship/bellship/blob/master/docker/Install_docker-ce_v1_0_191210.md

- docker-compose 설치
   > 설치 방법: https://ldccai.lotte.net/gitlab/bellship/bellship/blob/master/docker/Install_docker_compose_v1_0_191210.md

- CKAN 소스 다운로드
~~~
$
cd /path/to/my/projects
git clone https://github.com/ckan/ckan.git
cd ./ckan
git checkout tags/ckan-2.8.2
~~~

## 설치 및 초기 설정


## Ckan CLI
### 계정 관련
- 계정 명령어
~~~
$
docker exec -it ckan /usr/local/bin/ckan-paster \
--plugin=ckan sysadmin -c /etc/ckan/production.ini --help
~~~
* 계정 추가
>$  
docker exec -ti ckan /usr/local/bin/ckan-paster \\
--plugin=ckan \\
sysadmin \\
-c /etc/ckan/production.ini \\
add **userName** \\
email=**yourEmailname@yourDomain** \\
name=**yourName**

   docker exec -it ckan /usr/local/bin/ckan-paster --plugin=ckan sysadmin -c /etc/ckan/production.ini add johndoe

# Ckanext-s3filestore
- 전제
  - CKAN 버전 2.5 이상



# ckan harvesting
- 데이터 공유 플랫폼 CKAN에는 서로 다른 서버들간의 데이터를 주고 받을 수 있는 harvest라는 기능이 있다.
- 백엔드로 아래의 두 가지 소프트웨어를 사용할 수 있다.
  - Redis
  - RabbitMQ
  - 각자 사용하고 싶은 걸 사용해도 무방하지만, redis가 더 안정적이고 믿을 만 하다고 하기 때문에 CKAN org는 redis를 추천한다.
