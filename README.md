
# [JSON] Corona-19-API
![preview](https://user-images.githubusercontent.com/22024308/79011806-d1e9d300-7b9f-11ea-87bb-3be5126c2394.JPG)

코로나바이러스감염증-19 관련 API 서비스를 제공합니다.
- 24시간 운영(업타임: https://status.corona-19.kr)
- API 호출 수 제한 없음
- 공식 자료 사용(ncov.mohw.go.kr)

Corona-19-API 사용을 원하시면 README.md 문서를 확인하세요.
Corona-19-API 업데이트 로그 확인을 원하시면 update_log.md5 문서를 확인하세요.

## 👨‍💻 목차
- [서비스키 발급](https://github.com/dhlife09/Corona-19-API/blob/master/README.md#-0-%EC%84%9C%EB%B9%84%EC%8A%A4%ED%82%A4-%EB%B0%9C%EA%B8%89)
- [국내 정보](https://github.com/dhlife09/Corona-19-API/blob/master/README.md#-1-%EA%B5%AD%EB%82%B4-%EC%A0%95%EB%B3%B4)
	- [국내 카운터](https://github.com/dhlife09/Corona-19-API/blob/master/README.md#-1-1-%EA%B5%AD%EB%82%B4-%EC%B9%B4%EC%9A%B4%ED%84%B0)
	- [시도별 발생동향](https://github.com/dhlife09/Corona-19-API/blob/master/README.md#-1-2-%EC%8B%9C%EB%8F%84%EB%B3%84-%EB%B0%9C%EC%83%9D%EB%8F%99%ED%96%A5)
- [전세계 정보(준비중)](https://github.com/dhlife09/Corona-19-API/blob/master/README.md#-%EC%A0%84%EC%84%B8%EA%B3%84-%EC%A0%95%EB%B3%B4%EC%A4%80%EB%B9%84%EC%A4%91)
- [굿바이코로나 Corona-19-API 이용약관](https://github.com/dhlife09/Corona-19-API/blob/master/README.md#-%EA%B5%BF%EB%B0%94%EC%9D%B4%EC%BD%94%EB%A1%9C%EB%82%98-corona-19-api-%EC%9D%B4%EC%9A%A9%EC%95%BD%EA%B4%80)
- [굿바이코로나 Corona-19-API 개인정보처리방침](https://github.com/dhlife09/Corona-19-API/blob/master/README.md#-%EA%B5%BF%EB%B0%94%EC%9D%B4%EC%BD%94%EB%A1%9C%EB%82%98-corona-19-api-%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4%EC%B2%98%EB%A6%AC%EB%B0%A9%EC%B9%A8)
## 🔐 0. 서비스키 발급
### 1. 키 발급
- https://api.corona-19.kr/ 에 방문해서 이메일 주소, 사용 목적을 입력하신 후 "API 키 발급하기" 버튼을 눌러주세요.
- 버튼을 누르면 메일로 API 키가 발송됩니다.

## ✔ 1. 국내 정보
 ### 📙 1-1. 국내 카운터
  - 제공 정보: 국내 확진자수, 국내 완치자수, 국내 사망자수, 국내 격리자수, 확진환자 현황 상위 1-5 시도명 및 퍼센트율, 누적 검사수, 누적 검사완료수, 누적 확진률, 검사중/결과양성/결과음성 카운터 및 퍼센트 등
 - 정보 출처: http://ncov.mohw.go.kr/
 
```html
http://api.corona-19.kr/korea/?serviceKey=APIKey
```
#### ※ 요청변수 [GET]
|parameter|항목설명|요청 예제|
|---|---|--|
|serviceKey|API 인증키|http://api.corona-19.kr/korea/?serviceKey=fff098a39e0a841ab72e1d27bdee9b517|

#### ※ 응답내용
|항목명(영어)|항목명(한글)|비고|샘플데이터|
|---|---|--|--|
|resultCode|응답코드|정상(0) / 권한이 없거나 잘못된 키(401)|0|
|TotalCase|국내 확진자수|-|10,237|
|TotalRecovered|국내 완치자수|-|6,463|
|TotalDeath|국내 사망자수|-|183|
|NowCase|국내 격리자수|-|3,591|
|city1n|시도별 확진환자 현황1(이름)|시도별 확진환자 현황에서 1번째로 많은 확진환자가 있는 시도의 이름|대구|
|city2n|시도별 확진환자 현황2(이름)|시도별 확진환자 현황에서 2번째로 많은 확진환자가 있는 시도의 이름|경북|
|city3n|시도별 확진환자 현황3(이름)|시도별 확진환자 현황에서 3번째로 많은 확진환자가 있는 시도의 이름|기타|
|city4n|시도별 확진환자 현황4(이름)|시도별 확진환자 현황에서 4번째로 많은 확진환자가 있는 시도의 이름|경기|
|city5n|시도별 확진환자 현황5(이름)|시도별 확진환자 현황에서 5번째로 많은 확진환자가 있는 시도의 이름|서울|
|city1p|시도별 확진환자 현황1(퍼센트)|시도별 확진환자 현황에서 1번째로 많은 확진환자가 있는 시도의 퍼센트율|66.11|
|city2p|시도별 확진환자 현황2(퍼센트)|시도별 확진환자 현황에서 2번째로 많은 확진환자가 있는 시도의 퍼센트율|12.84|
|city3p|시도별 확진환자 현황3(퍼센트)|시도별 확진환자 현황에서 3번째로 많은 확진환자가 있는 시도의 퍼센트율|10.07|
|city4p|시도별 확진환자 현황4(퍼센트)|시도별 확진환자 현황에서 4번째로 많은 확진환자가 있는 시도의 퍼센트율|5.59|
|city5p|시도별 확진환자 현황5(퍼센트)|시도별 확진환자 현황에서 5번째로 많은 확진환자가 있는 시도의 퍼센트율|5.39|
|recoveredPercentage|국내 완치율|단위: 퍼센트|63.13|
|deathPercentage|국내 사망률|단위: 퍼센트|1.79|
|checkingCounter|국내 검사중|단위: 명|19,571|
|checkingPercentage|국내 검사중|단위: 퍼센트|4.2|
|caseCounter|국내 검사결과 양성|단위: 명|10,237|
|casePercentage|국내 검사결과 양성|단위: 퍼센트|2.2|
|notcaseCount|국내 검사결과 음성|단위: 명|431,425|
|notcasePercentage|국내 검사결과 음성|단위: 퍼센트|93.5|
|TotalChecking|총 검사완료 수|단위: 명|461,233|
|TodayRecovered|오늘 하루 완치자수|단위: 명|135|
|updateTime|정보 업데이트 기준|00시정보로 오전10시경 자동 업데이트 됩니다.|코로나바이러스감염증-19 국내 발생현황 (4.5. 00시 기준)|
|resultMessage|API 처리 결과|정상처리: (정상 처리되었습니다.) / 오류(권한이 없거나 잘못된 키 입니다. \"github.com\/dhlife09\/Corona-19-API\"에 방문하세요.)|정상 처리되었습니다.|

※ JSON 샘플 응답(전문)
- [https://github.com/dhlife09/Corona-19-API/blob/master/1_%EA%B5%AD%EB%82%B4%EC%B9%B4%EC%9A%B4%ED%84%B0_%EC%9D%91%EB%8B%B5%EC%83%98%ED%94%8C.json](https://github.com/dhlife09/Corona-19-API/blob/master/1_%EA%B5%AD%EB%82%B4%EC%B9%B4%EC%9A%B4%ED%84%B0_%EC%9D%91%EB%8B%B5%EC%83%98%ED%94%8C.json)

 
---

 ### 📙 1-2. 시도별 발생동향
  - 제공 정보: 전일대비 확진환자 증감, 확진환자수, 격리해제수, 사망자수, 발생률 등
 - 정보 출처: http://ncov.mohw.go.kr/
 
```html
http://api.corona-19.kr/korea/country/new/?serviceKey=APIKey
```
※ 요청변수 [GET]
|parameter|항목설명|예제|
|---|---|--|
|serviceKey|API 인증키|http://api.corona-19.kr/korea/country/new/?serviceKey=fff098a39e0a841ab72e1d27bdee9b517|

#### ※ 응답내용
|항목명(영어)|항목명(한글)|비고|샘플데이터|
|---|---|--|--|
|resultCode|응답코드|정상(0) / 권한이 없거나 잘못된 키(401)|0|
|resultMessage|정상처리: (정상 처리되었습니다.) / 오류(권한이 없거나 잘못된 키 입니다. \"github.com\/dhlife09\/Corona-19-API\"에 방문하세요.)|정상 처리되었습니다.|
|countryName|시도명(지역명)||서울|
|newCase|신규확진환자수|전일대비|2|
|totalCase|확진환자수||619|
|recovered|완치자수||250|
|death|사망자||2|
|percentage|발생률|단위: %|6.36|
|newFcase|전일대비증감-해외유입||1|
|newCcase|전일대비증감-지역발생||1|

※ JSON 샘플 응답(전문)
- [https://github.com/dhlife09/Corona-19-API/blob/master/2_%EC%8B%9C%EB%8F%84%EB%B3%84_%EB%B0%9C%EC%83%9D%EB%8F%99%ED%96%A5_%EC%9D%91%EB%8B%B5%EC%83%98%ED%94%8C.json](https://github.com/dhlife09/Corona-19-API/blob/master/2_%EC%8B%9C%EB%8F%84%EB%B3%84_%EB%B0%9C%EC%83%9D%EB%8F%99%ED%96%A5_%EC%9D%91%EB%8B%B5%EC%83%98%ED%94%8C.json)


## ❌ 전세계 정보(준비중)
### ❌ 1. 전세계 카운터
- 제공 정보: 전세계 확진자수, 전세계 완치자수, 전세계 사망자수, 전세계 현재 환자수
- 정보 출처: https://www.worldometers.info/coronavirus/index.php


## 📣 굿바이코로나 Corona-19-API 이용약관
- 굿바이코로나에서 제공하는 코로나19 관련 API는 누구나 무료로 제한없이 사용할 수 있습니다.
- 불법 서비스에서의 API 이용은 금지됩니다.
- 서비스에 부하를 주는 행위는 금지됩니다.
- 일회용 이메일과 같은 비정상적인 이메일 주소를 이용한 API 키 발급을 금지합니다.
- 키를 받으신 이메일 주소로 서비스 중요 공지사항 등은 발송될 수 있습니다.

## 📣 굿바이코로나 Corona-19-API 개인정보처리방침
<굿바이코로나>('https://api.corona-19.kr'이하 'Corona-19-API')_은(는) 개인정보보호법에 따라 이용자의 개인정보 보호 및 권익을 보호하고 개인정보와 관련한 이용자의 고충을 원활하게 처리할 수 있도록 다음과 같은 처리방침을 두고 있습니다.

<굿바이코로나>('Corona-19-API')_  은(는) 회사는 개인정보처리방침을 개정하는 경우 웹사이트 공지사항(또는 개별공지)을 통하여 공지할 것입니다.

○ 본 방침은부터  2020년 4월 1일부터 시행됩니다.

**(1). 개인정보의 처리 목적**  <굿바이코로나>('https://api.corona-19.kr'이하 'Corona-19-API')_은(는) 개인정보를 다음의 목적을 위해 처리합니다. 처리한 개인정보는 다음의 목적이외의 용도로는 사용되지 않으며 이용 목적이 변경될 시에는 사전동의를 구할 예정입니다.

가. 홈페이지 회원가입 및 관리
회원 가입의사 확인, 서비스 부정이용 방지 등을 목적으로 개인정보를 처리합니다.

나. 민원사무 처리
처리결과 통보 등을 목적으로 개인정보를 처리합니다.

**(2). 개인정보 파일 현황**  
1. 개인정보 파일명 : 굿바이코로나 Corona-19-API 개인정보  
- 개인정보 항목 : 이메일, 접속 IP 정보  
- 수집방법 : 홈페이지  
- 보유근거 : 안정적인 서비스 운영, 불법이용 방지  
- 보유기간 : 서비스 종료까지  

**3. 개인정보의 처리 및 보유 기간**  
  
①  <굿바이코로나>('Corona-19-API')은(는) 법령에 따른 개인정보 보유·이용기간 또는 정보주체로부터 개인정보를 수집시에 동의 받은 개인정보 보유,이용기간 내에서 개인정보를 처리,보유합니다.  
  
② 각각의 개인정보 처리 및 보유 기간은 다음과 같습니다.

1.<민원사무 처리>  
<민원사무 처리>와 관련한 개인정보는 수집.이용에 관한 동의일로부터<서비스 종료까지>까지 위 이용목적을 위하여 보유.이용됩니다.  
-보유근거 : 안정적인 서비스 운영, 불법이용 방지
  

**4. 정보주체와 법정대리인의 권리·의무 및 그 행사방법 이용자는 개인정보주체로써 다음과 같은 권리를 행사할 수 있습니다.**

① 정보주체는 굿바이코로나에 대해 언제든지 개인정보 열람,정정,삭제,처리정지 요구 등의 권리를 행사할 수 있습니다.  
② 제1항에 따른 권리 행사는굿바이코로나에 대해 개인정보 보호법 시행령 제41조제1항에 따라 전자우편을 통하여 하실 수 있으며 굿바이코로나은(는) 이에 대해 지체 없이 조치하겠습니다.  
③ 제1항에 따른 권리 행사는 정보주체의 법정대리인이나 위임을 받은 자 등 대리인을 통하여 하실 수 있습니다. 이 경우 개인정보 보호법 시행규칙 별지 제11호 서식에 따른 위임장을 제출하셔야 합니다.  
④ 개인정보 열람 및 처리정지 요구는 개인정보보호법 제35조 제5항, 제37조 제2항에 의하여 정보주체의 권리가 제한 될 수 있습니다.  
⑤ 개인정보의 정정 및 삭제 요구는 다른 법령에서 그 개인정보가 수집 대상으로 명시되어 있는 경우에는 그 삭제를 요구할 수 없습니다.  
⑥ 굿바이코로나은(는) 정보주체 권리에 따른 열람의 요구, 정정·삭제의 요구, 처리정지의 요구 시 열람 등 요구를 한 자가 본인이거나 정당한 대리인인지를 확인합니다.

**5. 처리하는 개인정보의 항목 작성**  
  
①  <굿바이코로나>('https://api.corona-19.kr'이하 'Corona-19-API')_은(는) 다음의 개인정보 항목을 처리하고 있습니다.

1. <민원사무 처리>  
- 필수항목 : 이메일, 접속 IP 정보 

**6. 개인정보의 파기 <굿바이코로나>('Corona-19-API')_은(는) 원칙적으로 개인정보 처리목적이 달성된 경우에는 지체없이 해당 개인정보를 파기합니다. 파기의 절차, 기한 및 방법은 다음과 같습니다.**

-파기절차  
이용자가 입력한 정보는 목적 달성 후 별도의 DB에 옮겨져(종이의 경우 별도의 서류) 내부 방침 및 기타 관련 법령에 따라 일정기간 저장된 후 혹은 즉시 파기됩니다. 이 때, DB로 옮겨진 개인정보는 법률에 의한 경우가 아니고서는 다른 목적으로 이용되지 않습니다.  
  
-파기기한  
이용자의 개인정보는 개인정보의 보유기간이 경과된 경우에는 보유기간의 종료일로부터 5일 이내에, 개인정보의 처리 목적 달성, 해당 서비스의 폐지, 사업의 종료 등 그 개인정보가 불필요하게 되었을 때에는 개인정보의 처리가 불필요한 것으로 인정되는 날로부터 5일 이내에 그 개인정보를 파기합니다.

-파기방법  
전자적 파일 형태의 정보는 기록을 재생할 수 없는 기술적 방법을 사용합니다.

  
  

**7. 개인정보 자동 수집 장치의 설치•운영 및 거부에 관한 사항**

굿바이코로나 은 정보주체의 이용정보를 저장하고 수시로 불러오는 ‘쿠키’를 사용하지 않습니다.  
  

**8. 개인정보 보호책임자 작성**

  
① 굿바이코로나(‘https://api.corona-19.kr’이하 ‘Corona-19-API) 은(는) 개인정보 처리에 관한 업무를 총괄해서 책임지고, 개인정보 처리와 관련한 정보주체의 불만처리 및 피해구제 등을 위하여 아래와 같이 개인정보 보호책임자를 지정하고 있습니다.

  
▶ 개인정보 보호책임자  
성명 :박도현  
직책 :운영자  
직급 :운영자  
연락처 : +82-10-507-1308-1684(0507-1308-1684), dhlife09@gmail.com
※ 개인정보 보호 담당부서로 연결됩니다.  
  
② 정보주체께서는 굿바이코로나(‘https://api.corona-19.kr’이하 ‘Corona-19-API) 의 서비스(또는 사업)을 이용하시면서 발생한 모든 개인정보 보호 관련 문의, 불만처리, 피해구제 등에 관한 사항을 개인정보 보호책임자로 문의하실 수 있습니다. 굿바이코로나(‘https://api.corona-19.kr’이하 ‘Corona-19-API) 은(는) 정보주체의 문의에 대해 지체 없이 답변 및 처리해드릴 것입니다.  d

**9. 개인정보 처리방침 변경**

① 이 개인정보처리방침은 시행일로부터 적용되며, 법령 및 방침에 따른 변경내용의 추가, 삭제 및 정정이 있는 경우에는 변경사항의 시행 7일 전부터 공지사항을 통하여 고지할 것입니다.

**10. 개인정보의 안전성 확보 조치  <굿바이코로나>('Corona-19-API')은(는) 개인정보보호법 제29조에 따라 다음과 같이 안전성 확보에 필요한 기술적/관리적 및 물리적 조치를 하고 있습니다.**

1. 접속기록의 보관 및 위변조 방지  
개인정보처리시스템에 접속한 기록을 최소 6개월 이상 보관, 관리하고 있으며, 접속 기록이 위변조 및 도난, 분실되지 않도록 보안기능 사용하고 있습니다.  
  
2. 개인정보에 대한 접근 제한  
개인정보를 처리하는 데이터베이스시스템에 대한 접근권한의 부여,변경,말소를 통하여 개인정보에 대한 접근통제를 위하여 필요한 조치를 하고 있으며 침입차단시스템을 이용하여 외부로부터의 무단 접근을 통제하고 있습니다.
