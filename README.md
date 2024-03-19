# myproject_3rd
세번째 프로젝트 - team K-Karina Univ.

조원 - 김하린아, 문원선, 한찬희, 황지현

프로젝트 기간 - 2023.12.26 ~ 2024.02.06

담당 업무 - Terraform, Kubernetes, Monotoring(Prometheus & Grafana), AWS WAF

-- Terrafrom --       #college_terraform_space 디렉토리
Terraform(main.tf)을 사용하여 코드로 AWS에서 제공하는 서비스들을 상황에 맞는 설정들을 추가하며 구성
코드로써 인프라를 관리하였기때문에 일관성있는 인프라의 유지 및 관리가 가능

-- Kubernetes --      #college_kube_space 디렉토리
Kubernetes에서 pod의 유지관리는 ArgoCD를 통해 일정수준의 pod를 자동으로 유지할 수 있도록 구성하였으며, AWS의 정책과 관련된 부분(IRSA)은 관리자가 직접 작성하면서 관리하도록 분류.
외부 사용자들이 pod들에 접근할 수 있도록 ingress의 load balancer를 도메인과 연결함으로써 외부에 노출시켜주었고, 사용자의 요청URL을 service에 명시하여 최종적으로 사용자들이 원하는 기능을 가진 pod들에 접근


-- Monotoring(Prometheus & Grafana) --      #college_kube_space/k8s-prometheus-main 디렉토리
Prometheus는 직접 pod로 실행하여 kube-state의 metric 지표를 수집할 수 있도록 구성

Grafana는 Bastion Host에 설치하였으며  Bastion Host는 AutoScaling으로 일관성있게 유지되도록 구성. 이로인해 보다 더 안정적으로 Prometheus의 지표들을 관찰할 수 있도록 구성

-- AWS WAF --
AWS WAF서비스에서 제공하는 IP평판 목록과 악성IP 차단 규칙을 사용하여 봇으로 알려져있거나 악성 사용자의 IP에서의 접근을 차단
