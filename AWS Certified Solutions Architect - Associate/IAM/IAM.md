IAM 개요
- AWS 계정!!!! 및 권한 관리!!!!! 서비스  
- AWS 서비스와 리소스에 대한 액세스 관리  
- 사용자, 그룹, 역할, 정책으로 구성  
- 리전에 속하는 서비스가 아닌 글로벌 서비스
- 계정 보안 강화를 위해
- 루트 계정(AWS회원가입시 만들어지는 계정)은 최초 사용자 계정 생성 이후 가능하면 사용하지 말 것
- 사용자 계정(IAM 계정)으로 서비스를 사용하고 사용자는 필요한 최소한의 권한만 부여(최소권한의 원칙)
- 루트계정과 개별 사용자 계정에 강력한 암호 정책과 멀티팩터 인증(MFA) 적용
- 사용자의 암호에 대한 복잡성 요구 사항과 의무 교체 주기를 정의

![image](https://user-images.githubusercontent.com/67897827/181002539-54f0bb40-6f4f-4e57-b77e-3940138eeadd.png)

- IAM에서 사용자를 만들어서 그걸로 로그인 할 수 있다.
 
 IAM - 정책  
• AWS 리소스에 대한 액세스 권한을 정의 한 것  
• 사용자, 그룹, 역할에 정책을 연결하여 사용  
• JSON 문서 형식으로 이루어짐  
• 정책이 명시되지 않는 경우 기본적으로 모든 요청이 거부(Deny)됨  
IAM 정책 JSON 문서 구조  
➢ Effect : Statement에 대한 Access 또는 Deny  
➢ Action: 권한에 대한 작업 목록  
➢ Resource: 권한이 적용되는 리소스  
➢ Condition: 정책이 적용되는 세부 조건 (옵션사항)  

![image](https://user-images.githubusercontent.com/67897827/181007379-6fe0cb79-002d-4580-9a7b-b989a9516ed7.png)

![image](https://user-images.githubusercontent.com/67897827/181007781-bcf80b5d-b171-41d4-9da9-5ceb18d5e08f.png)

- 이것은 AWS사용자 들어가서 권한에 Permissons boundary 경계설정 해서 경계를 주게 되면 이 사용자는 월래 받은 정책권한과 여기서 받은것의 교집합으로 권한 설정됨.


IAM - 역할  
• AWS 리소스에서 사용하는 자격증명  
• 특정 AWS 서비스가 다른 AWS 서비스에 액세스 하여 작업을 수행할 때 필요한 권한!!!!!  
• 정책을 연결하여 IAM 역할에 작업 수행에 필요한 권한을 부여  
• 만일, EC2에서 실행되는 애플리케이션이 AWS S3와 AWS RDS 액세스 권한이 필요할 때 역할 사용  

![image](https://user-images.githubusercontent.com/67897827/181011007-5cfde212-3241-47b9-964d-cbb58e789175.png)


IAM – 역할 (신뢰정책)  
• IAM 역할을 사용하여 AWS 계정간 액세스 권한 위임을 하는 기능  
• 신뢰 정책 (Trust Policy) 을 사용하여 다른 AWS 계정에 역할을 위임할 수 있음  

AWS 역할들어가서 신뢰관계 찾아서 다른 계정에 역할을 위임할수있다 즉 다른 계정에서 이 계정으로 먼가 푸쉬할때 사용된다!!
또 중요한것이 EC2만들때도 IAM역할에 역할만든거 연결해줘야 이 만든 EC2가 다른 서비스에 Access할 수 있는 것이다.
