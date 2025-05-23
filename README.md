# DO-LAB 이란?
## **1단계: 프로젝트의 핵심 목적 정의**
### 1. 이 프로젝트가 해결하고자 하는 문제는 무엇인가?
현재 **Google Colab**은 원격으로 Python 코드를 실행할 수 있는 강력한 플랫폼이지만, 다음과 같은 **제한 사항**이 있다.
#### **Google Colab의 장점**
- 원격으로 Jupyter Notebook 환경을 사용할 수 있음.
- 로컬 컴퓨터를 켜놓지 않아도 장시간 코드 실행 가능.
- Linux 기반 환경에서 최신 AI 라이브러리 사용 가능.
- 제한적이지만 무료 GPU 사용 가능.
- Google Drive 연동이 용이하며 협업 지원.
#### **Google Colab의 한계점**
- 제공된 컴퓨팅 자원을 모두 소진하면 일정 시간 이후 다시 사용해야 함.
- **무료 사용자는 일정 시간 동안 입력이 없으면 세션이 자동 종료됨.**
- 고사양 GPU/TPU는 **월 구독제 요금제로만 제공됨** (사용량 기반 결제 X).
- **보안 문제**: 모든 코드가 Google 서버에서 실행되므로 민감한 데이터 처리에 부적합.

**DO-LAB**은 **Google Colab의 장점을 유지하면서도 단점을 보완**하는 솔루션이다.
#### **핵심 목표**:
- 사용자의 **Linux 기반 개인 서버(또는 클라우드 서버)를 활용하여 원격 Jupyter Notebook 환경 제공**.
- 로컬 GPU를 사용할 수 있으며, **필요할 때만 RunPod 등의 GPU 대여 서비스를 활용**하여 비용 절감.
- **다중 사용자 격리 환경**을 제공하여 **한 개의 서버를 여러 사람이 독립적으로 활용 가능**.
- **보안 강화**: 코드가 신뢰할 수 있는 개인 서버에서 실행되므로 데이터 유출 우려 없음.

### 2. 최종 사용자는 누구인가?
DO-LAB이 주로 필요한 대상은 다음과 같다.
1. **지속적으로 코드 실행이 필요한 개발자**
    - 모델 훈련, 데이터 처리 등의 이유로 **장시간 코드 실행이 필요한 사람**.
2. **최신 AI 라이브러리가 필요한 인공지능 개발자**
    - Google Colab이 제공하는 환경을 넘어 **맞춤형 AI 환경을 구축하고 싶은 사용자**.
3. **고성능 GPU가 없는 개발자**
    - 로컬 컴퓨터에 **고사양 GPU가 없어도 클라우드 GPU를 필요할 때만 활용 가능**.
4. **GPU를 지속적으로 사용하지 않는 사용자**
    - **GPU가 항상 필요한 것이 아니라 특정 프로젝트 진행 시에만 필요**한 연구자 및 개발자.
    - 불필요한 구독 요금 없이 **사용한 만큼만 비용을 지불**할 수 있도록 GPU 대여 플랫폼과 연동 가능.

### 3. 프로젝트의 주요 기능은 어떤 것들이 있는가?
#### **원격 Jupyter Notebook 실행**
- 사용자의 **리눅스 서버**에서 Jupyter Notebook을 실행하여 원격으로 접속 가능하게 함.
- 웹 브라우저에서 접근 가능하며, GUI 없이 터미널에서도 실행 가능.
#### **GPU 및 컴퓨팅 자원 선택적 활용**
- 사용자의 로컬 GPU를 활용하여 연산 가능.
- **RunPod과 같은 GPU 대여 서비스와 연동**하여 필요할 때만 외부 GPU 사용.
- GPU 사용량을 실시간으로 모니터링하고 제어할 수 있도록 설정.
#### **자동 세션 유지 및 중단 방지**
- 일정 시간 동안 입력이 없을 경우에도 **세션을 자동 유지**하는 기능.
- 사용자가 지정한 시간까지 실행 후 자동 종료하는 기능.
- 코드 실행 중에 사용자가 원격으로 지속적으로 모니터링 가능.
#### **다중 사용자 환경 지원**
- 하나의 서버에서 **다수의 사용자**가 독립적으로 환경을 사용할 수 있도록 격리 시스템 구축.
- 각 사용자별로 **개별적인 환경(가상 환경, Docker 컨테이너 등)을 제공**하여 충돌 방지.
#### **보안 및 데이터 보호**
- 사용자의 **로컬 서버에서 코드가 실행되므로 보안이 강화됨**.
- SSH를 이용한 암호화된 접속 방식 제공.
- 필요 시 VPN을 활용하여 원격 접속 지원.
- 사용자의 코드와 데이터는 외부 클라우드에 저장되지 않음.
#### **클라우드 및 저장소 연동**
- 사용자가 원할 경우, Google Drive, AWS S3 등과 연동하여 파일 저장 가능.
- 코드 실행 결과를 자동으로 저장하고 백업하는 기능.
#### **쉬운 설치 및 설정**
- 간단한 명령어 몇 개만 실행하면 DO-LAB을 설치하고 사용할 수 있도록 구성.
- GUI 기반의 설정 페이지를 제공하여 서버 환경을 쉽게 조정 가능.
#### **확장성과 유연성 제공**
- 로컬 컴퓨터뿐만 아니라 **리눅스 기반의 클라우드 서버(AWS, GCP, Azure)에서도 동작 가능**.

### 4. 이 프로젝트를 사용함으로써 사용자가 얻을 주요 가치는 무엇인가?
#### **1) 비용 절감**
- Google Colab처럼 월 정액 요금이 아닌, 사용자의 **로컬 서버나 필요할 때만 GPU 대여 서비스를 사용하여 비용 절감**.
- 고가의 GPU를 구매하지 않아도 **일정 시간만 GPU를 대여해서 사용할 수 있음**.
#### **2) 높은 유연성과 자유도**
- 사용자의 컴퓨터 환경에 맞춰 원하는 **버전의 인공지능 라이브러리, 패키지, 툴을 자유롭게 설치 가능**.
- Google Colab처럼 특정 버전에 묶이지 않고, 원하는 환경을 설정할 수 있음.
#### **3) 데이터 및 코드 보안**
- 모든 코드가 **사용자의 신뢰할 수 있는 서버에서 실행되므로 보안 우려가 적음**.
- Google Colab처럼 모든 데이터가 외부 클라우드에 저장되지 않으므로 **기업 내부 데이터, 연구용 코드 등도 안전하게 실행 가능**.
#### **4) 지속적인 코드 실행 가능**
- Google Colab에서는 일정 시간이 지나면 **자동으로 세션이 종료**되지만, DO-LAB에서는 사용자가 지정한 **시간 동안 지속 실행 가능**.
- SSH 또는 웹 UI를 통해 원격에서 실행 상태를 확인하고 **필요할 때 다시 접속 가능**.
#### **5) 협업과 멀티 사용자 지원**
- 여러 사용자가 **하나의 서버에서 독립적인 환경을 사용할 수 있도록 지원**.
- 연구실, 스타트업, 팀 단위 프로젝트에서 GPU 자원을 공유하면서도 개별 환경을 유지할 수 있음.
#### **6) 빠른 프로토타이핑 및 실험 가능**
- AI 연구자 및 개발자가 **자신의 로컬 서버에서 실험을 신속하게 진행 가능**.
- GPU 사용이 필요한 코드도 빠르게 테스트하고 배포 가능.

---

## **2단계: 핵심 기능과 요구사항 구체화**
### 5. 필수적인 기능(핵심 기능)과 선택적 기능(부가 기능)을 나눠볼 수 있는가?
#### 핵심 기능
1. **원격 Jupyter Notebook 실행 지원**
	- 사용자의 **로컬 컴퓨터에서 Jupyter Notebook 환경을 실행**하고, 외부에서 접속 가능하도록 지원.
	- 웹 브라우저를 통해 원격으로 접근할 수 있도록 설정.
	- SSH 터널링 또는 VPN을 활용한 보안 접속 제공.
2. **GPU 대여 서비스와 연동 (RunPod, Lambda Labs 등)**
	- 사용자의 **로컬 GPU를 활용하거나, 필요할 때만 GPU를 대여하여 사용**할 수 있도록 설정.
	- GPU 사용량을 실시간으로 모니터링하고, 특정 시간 후 자동 종료 기능 제공.
	- 사용자가 직접 GPU 대여 옵션을 선택할 수 있도록 인터페이스 제공.
#### 부가 기능
3. **클라우드 시스템 연동** (Google Drive, AWS S3, Dropbox 등)
	- 사용자가 작업 데이터를 편리하게 저장하고 불러올 수 있도록 **클라우드 스토리지 연동 지원**.
	- 학습된 모델을 클라우드에 자동 백업하는 기능 추가 가능.
4. **외부 클라우드 서버(AWS, GCP, Azure)에서의 실행 간편화**
	- 사용자의 로컬 컴퓨터뿐만 아니라 **AWS, GCP, Azure 등의 클라우드 인스턴스에서 쉽게 실행 가능하도록 지원**.
	- Terraform, Ansible 등의 자동 배포 스크립트를 제공하여 빠른 환경 구성 가능.
5. **사용자 간 격리된 환경 제공**
	- 한 개의 서버에서 **여러 사용자가 독립적인 환경에서 DO-LAB을 사용할 수 있도록 격리 시스템 구현**.
	- **Docker 컨테이너 또는 가상 환경(Virtual Environment) 기반의 격리 지원**.
6. **협업 환경 조성**
	- **여러 사용자가 동시에 같은 프로젝트를 편리하게 공유하고 협력할 수 있도록 기능 추가**.
	- 실시간 협업을 위한 **Jupyter Notebook 공유 기능**.
	- 권한 관리 기능 (예: 읽기 전용, 실행 가능, 수정 가능 등).

### 6. 사용자가 이 기능을 어떻게 사용할지 간단한 시나리오를 만들어볼 수 있는가?
#### 자신의 컴퓨터에 설치하는 경우
- DO-LAB을 로컬 컴퓨터에 설치하고, Jupyter Notebook을 원격으로 접근하여 실행.
- 로컬의 CPU 또는 GPU를 활용하여 코드 실행
- VPN 또는 SSH를 통해 보안 접속 지원.
#### AWS와 같은 클라우드 컴퓨터에 설치하는 경우
- 사용자가 AWS, GCP, Azure 등의 클라우드 인스턴스를 생성하고, DO-LAB을 설치하여 실행.
- 사용자의 설정에 따라 클라우드에서 CPU 또는 GPU를 활용.
#### GPU를 사용하지 않는 경우
- DO-LAB을 CPU 환경에서 실행하여 가벼운 데이터 분석 및 모델 개발 진행.
- Google Colab처럼 원격으로 코드 실행 가능하지만, GPU를 사용하지 않음.
#### GPU를 사용하고 자신의 컴퓨터에 GPU가 설치되어있는 경우
- DO-LAB을 로컬 컴퓨터에 설치하고, 내장 GPU를 활용하여 실행.
- GPU 종류에 맞는 드라이버 설치.
- GPU 사용량 실시간 모니터링.
#### 로컬에서 실행하되, GPU를 대여 시스템을 통해 대여하는 경우
- DO-LAB이 RunPod와 같은 GPU 대여 플랫폼과 연동.
- 사용자가 필요할 때만 GPU를 임대하여 사용하고, 비용을 절감.
#### 클라우드 컴퓨터를 사용하되, GPU를 대여 시스템을 통해 대여하는 경우
- 클라우드 컴퓨터를 사용하면 사용 시간에 따른 요금이 부과되므로 GPU 대여 서비스를 사용하고 있는 동안 클라우드 컴퓨터에 관한 조치에 대해 생각해 보아야함.
#### 연구실 또는 팀 단위에서 서버를 공동으로 사용하는 경우
- 연구실 또는 스타트업 팀에서 공용 서버를 두고 여러 사용자가 독립적인 환경에서 실행.
- 각 사용자별로 Docker 컨테이너 또는 가상 환경을 할당하여 충돌 방지.
- GPU 리소스를 팀원 간 공유 및 예약 시스템을 통해 활용.

### 7. 성능, 보안, 확장성 등에서 중요한 비기능적 요구사항은 무엇인가?
#### 성능
- 응답 속도: 원격 Jupyter Notebook이 사용자가 실행을 요청한 후 최소한의 지연 시간으로 실행되어야 함.
- 최대 동시 사용자 수: 하나의 서버에서 여러 사용자가 동시에 사용할 때 성능 저하가 없도록 설계.
#### 보안
- 접근 제어: SSH, VPN, 사용자 인증 기능을 통해 허가된 사용자만 접근 가능하도록 설정.
- 네트워크 보안: 방화벽 및 접근 제어 정책 설정.
- 사용자별 격리 환경 제공: Docker, 가상 환경 등을 통해 사용자 간 실행 환경을 격리하여 보안 강화.
#### 확장성
- 다중 사용자 지원: 연구실, 스타트업 팀에서 여러 사용자가 동시에 사용할 수 있도록 수평 확장 지원.
#### 유지보수성
- 로딩 및 디버깅 기능 제공: 사용자가 문제가 발생했을 때, 문제 해결을 위한 로그 및 디버깅 도구 제공.
#### 사용성
- 쉬운 UI/UX 제공: 웹 기반의 관리 페이지를 제공하여 CLI를 사용하지 않아도 설정을 쉽게 변경할 수 있도록 지원.
- 초보자 친화적인 환경 제공: Google Colab과 유사한 인터페이스 및 명령어 지원.
- 다양한 디바이스에서 접속 가능: PC 뿐만 아니라 태블릿, 모바일에서도 원격으로 실행 및 모니터링 가능해야 함.
#### 비용 관리
- 사용한 만큼만 비용을 지불하는 모델 제공: 클라우드 GPU 대여 시스템과 연동하여 필요한 시간만 GPU를 사용하고 비용을 절감할 수 있도록 지원.
- 리소스 사용 최적화: 비활성 세션이 있다면 사용자에게 알려주어 불필요한 리소스 낭비 방지.

### 8. 프로젝트의 목표 일정과 예산은 어느 정도인가?
#### 목표 일정
- 제안서: 4월 2일
	- DO-LAB의 기본적인 구조와 기술 스택, 시스템 구성 등을 결정
	- 제안서 발표자료 제작
- 중간 발표: 5월 7일
	- 필수 기능 제작
- 최종 발표: 6월 18일
	- 필수 기능 보완
	- 추가 기능 제작
#### 예산
- 없음

---

## **3단계: 기술 스택과 시스템 구성 고려**

### 9. 이 프로젝트에서 가장 중요한 기술 스택(Java, Python, React, AWS 등)은 무엇인가?
- 주 개발 언어: Python
- 원격 코드 실행 환경 제공: Jupyter Notebook
	- JupyterLab + JupyterHub
- 컨테이너 기반 사용자 환경 격리: Docker / Podman
- 웹 API 백엔드: FastAPI / Flask (Python으로 개발 시) / Node.js 기반 API
- GPU 지원
	- 로컬 GPU 지원
		- NVIDIA CUDA + Pytorch / Tensorflow
		- CUDA / cuDNN
		- NVIDIA Container Toolkit -> Docker 내에서 GPU 연산 지원
	- 클라우드 GPU 지원
		- RunPod API
		- Lambda Labs API
		- vast.ai API
- 모니터링 및 로그 관리
	- Prometheus + Grafana (모니터링)
	- Logstash + ELK Stack (코드 로그 및 오류 기록)
- 웹 프론트엔드
	- React.js / Next.js
	- TailwindCSS / Material-UI
	- WebSocket

### 10. 프론트엔드와 백엔드를 어떻게 나눌 것인가? (예: 웹 앱, 모바일 앱, REST API 등)

### 11. 데이터베이스는 어떤 종류를 사용할 것인가? (SQL vs NoSQL)

### 12. 이 프로젝트에 필요한 외부 서비스(API, 클라우드, 결제 시스템 등)는 무엇인가?


---

### **4단계: 시스템 아키텍처 구상**

13. 프로젝트의 전체적인 구조는 어떤 형태인가? (모놀리식 vs 마이크로서비스)
14. 사용자 요청이 어떻게 흐르는가? (클라이언트 → 서버 → 데이터베이스)
15. 주요 컴포넌트(프론트엔드, 백엔드, 데이터베이스 등)는 어떻게 연결되는가?
16. 데이터 흐름과 저장 방식은 어떻게 설계할 것인가?

---

### **5단계: 프로토타입 및 MVP 설정**

17. 최소 기능 제품(MVP, Minimum Viable Product)으로 구현할 핵심 기능은 무엇인가?
18. 사용자 테스트를 위해 어떤 방식으로 프로토타입을 만들 것인가?
19. 피드백을 어떻게 수집하고 반영할 것인가?
20. 프로젝트의 초기 성공 기준은 무엇인가?

---

### **6단계: 배포 및 운영 계획**

21. 프로젝트를 어디에 배포할 것인가? (AWS, Azure, GCP, 온프레미스 등)
22. CI/CD(지속적 통합/지속적 배포) 파이프라인을 어떻게 설정할 것인가?
23. 운영 중 발생할 수 있는 주요 리스크(서버 장애, 보안 문제 등)는 무엇인가?
24. 모니터링과 로깅은 어떤 방식으로 설정할 것인가?