# myproject_3rd
세번째 프로젝트 - team K-Karina Univ.

조원 - 김하린아, 문원선, 한찬희, 황지현

프로젝트 기간 - 2023.12.26 ~ 2024.02.06

담당 업무 - Terraform, Kubernetes, Prometheus, Grafana, AWS WAF

Terraform(main.tf)을 사용하여 코드로 일관성있는 인프라의 유지 관리 관리자의 상황에 맞는 인프라 구성

Kubernetes에서 pod의 유지관리는 ArgoCD를 통해 일관성있는 pod의 유지 자동화를 하였으며, AWS의 정책과 관련된 부분은 관리자가 직접적으로 관리하여 구성

Monotoring

Prometheus는 직접 pod로 실행하여 kube-state의 metric 지표를 수집하도록 구성

Grafana는 Bastion Host에 설치하였으며  Bastion Host는 AutoScaling으로 일관성있게 유지되도록 구성. 이로인해 보다 더 안정적으로 Prometheus의 지표들을 관찰할 수 있도록 구성하였습니다.
