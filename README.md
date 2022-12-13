# FundManagement
금융조회 API
## 1 소개  
### 1.1 예금주조회
농협계좌에 대한 예금주정보를 인터넷뱅킹이나 펌뱅킹을 이용하지 않고 오픈API를 통해 실시간으로 조회할 수 있는 서비스입니다.
#### 1.1.1 예금주조회 NH API 목록
| 전문명 | API |
|:---:|:---:|
| 예금주 조회(계좌번호)	| InquireDepositorAccountNumber |

#### 1.1.2 출금이체 흐름도
![image](https://user-images.githubusercontent.com/51725751/72026781-183d4680-32c0-11ea-8570-a98df11490e5.png)


### 1.2 타행예금주조회
타행계좌에 대한 예금주정보를 인터넷뱅킹이나 펌뱅킹을 이용하지 않고 오픈API를 통해 실시간으로 조회할 수 있는 서비스입니다.
#### 1.2.1 타행예금주조회 NH API 목록
| 전문명 | API |
|:---:|:---:|
| 예금주실명확인(계좌번호) |	CheckDepositorAccountNumber |	

#### 1.2.2 입금이체 흐름도
![image](https://user-images.githubusercontent.com/51725751/72026919-8aae2680-32c0-11ea-9571-a8f3c5744afa.png)


### 1.3 잔액조회
핀-어카운트 연결계좌에 대한 잔액을 조회합니다.
#### 1.3.1 잔액조회 NH API 목록
| 전문명 | API |
|:---:|:---:|
| 잔액조회(핀어카운트) |	InquireBalance |	
		
#### 1.3.2 잔액조회 흐름도
![image](https://user-images.githubusercontent.com/51725751/72026989-c34e0000-32c0-11ea-93f3-700248cffe72.png)


### 1.4 개인카드조회
개인 신용/체크카드 관련 한도조회, 승인내역조회, 청구서목록 조회, 청구서 상세조회 등을 제공하는 서비스입니다.
#### 1.4.1 개인카드조회 NH API 목록
| 전문명 | API |
|:---:|:---:|
| 개인카드 승인내역조회 |	InquireCreditCardAuthorizationHistory |	
		
#### 1.4.2 개인카드조회 흐름도
![image](https://user-images.githubusercontent.com/51725751/72027095-16c04e00-32c1-11ea-83e3-945a5fbc4d6c.png)



## 2 resource url
#### 2.1 예금주조회
https://developers.nonghyup.com/InquireDepositorAccountNumber.nh
#### 2.2 타행예금주조회
https://developers.nonghyup.com/CheckDepositorAccountNumber.nh
#### 2.3 잔액조회
https://developers.nonghyup.com/InquireBalance.nhh
#### 2.4 개인카드조회
https://developers.nonghyup.com/InquireCreditCardAuthorizationHistory.nh



## 3 example
### 3.1.1 예금주조회 Request example
```json
{
    "Header":{
        "ApiNm":"InquireDepositorAccountNumber",
        "Tsymd":"20191129",
        "Trtm":"003544",
        "Iscd":"000019",
        "FintechApsno":"001",
        "ApiSvcCd":"DrawingTransferA",
        "IsTuno":"201911290000000001",
        "AccessToken":
        "791c18f7377be31c8b30b27eba8573de0aac529890c7b18ac722f6120adc5054"
        },
        "Bncd":"011",
        "Acno":"3020000000109"                
}
```
### 3.1.2 예금주조회 Request Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---:|:---:|:---:|:---:|:---:|:---:|  
| Header || 공통부 |||||	 
| Bncd |	은행코드 |	필드 |	3 |	필수 |	 
| Acno |	계좌번호 |	필드 |	20 |	필수 |	 	 
### 3.1.3 예금주조회 Response example
```json
{
    "Header": {
        "Trtm": "003544",
        "Rsms": "정상처리 되었습니다.",
        "ApiNm": "InquireDepositorAccountNumber",
        "IsTuno": "201911290000000001",
        "Tsymd": "20191129",
        "FintechApsno": "001",
        "Iscd": "000019",
        "Rpcd": "00000",
        "ApiSvcCd": "DrawingTransferA"
    },
    "Bncd": "011",
    "Dpnm": "홍길동",
    "Acno": "3020000000109"
}
```
### 3.1.4 예금주조회 Response Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---:|:---:|:---:|:---:|:---:|:---:|  
| Header || 공통부 |||||	 
| Bncd |	은행코드 |	필드 |	3 |	필수 |	 
| Acno |	계좌번호 |	필드 |	20 |	필수 |	 
| Dpnm |	예금주명 |	필드 |	50 |	필수 |

### 3.2.1 타행예금주조회 Request example
```json
{
    "Header":{
        "ApiNm":"InquireDepositorOtherBank",
        "Tsymd":"20191129",
        "Trtm":"003544",
        "Iscd":"000019",
        "FintechApsno":"001",
        "ApiSvcCd":"DrawingTransferA",
        "IsTuno":"201911290000000001",
        "AccessToken":
        "791c18f7377be31c8b30b27eba8573de0aac529890c7b18ac722f6120adc5054"
        },
    "Bncd":"002",
    "Acno":"1000000028002"
}
```
### 3.2.2 타행예금주조회 Request Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---:|:---:|:---:|:---:|:---:|:---:|  
| Header || 공통부 |||||	 
| Bncd |	은행코드 |	필드 |	3 |	필수 |	 
| Acno |	계좌번호 |	필드 |	20 |	필수 |	 
### 3.2.3 타행예금주조회 Response example
```json
{
    "Header": {
        "Trtm": "003544",
        "Rsms": "정상처리 되었습니다.",
        "ApiNm": "InquireDepositorOtherBank",
        "IsTuno": "201911290000000001",
        "Tsymd": "20191129",
        "FintechApsno": "001",
        "Iscd": "000019",
        "Rpcd": "00000",
        "ApiSvcCd": "DrawingTransferA"
    },
    "Bncd": "002",
    "Dpnm": "홍길동",
    "Acno": "1000000028002"
}
```
### 3.2.4 타행예금주조회 Response Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---:|:---:|:---:|:---:|:---:|:---:|  
| Header || 공통부 |||||	 
| Bncd |	은행코드 |	필드 |	3 |	필수 |	 
| Acno |	계좌번호 |	필드 |	20 |	필수 |	 
| Dpnm |	예금주명 |	필드 |	50 |	필수 |

### 3.3.1 잔액조회 Request example
```json
{
    "Header": {
        "ApiNm": "InquireBalance",
        "Tsymd": "20191212",
        "Trtm": "112428",
        "Iscd": "000013",
        "FintechApsno": "001",
        "ApiSvcCd": "ReceivedTransferA",
        "IsTuno": "1233424",
        "AccessToken": "10b74dd7f5f0f521ecdc7ade82f793bdfc119c3635d2e5303ae6aba0c93d4246"
    },
    "FinAcno": "00820100000130000000000002067"
}
```
### 3.3.2 잔액조회 Request Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---:|:---:|:---:|:---:|:---:|:---:|  
| Header || 공통부 |||||	 
| FinAcno |	핀-어카운트 |	필드 |	30 |	필수 |	  
### 3.3.3 잔액조회 Response example
```json
{
    "Header": {
        "Trtm": "112428",
        "Rsms": "정상처리 되었습니다.",
        "ApiNm": "InquireBalance",
        "IsTuno": "1233424",
        "Tsymd": "20191212",
        "FintechApsno": "001",
        "Iscd": "000013",
        "Rpcd": "00000",
        "ApiSvcCd": "ReceivedTransferA"
    },
    "FinAcno": "00820100000130000000000002067",
    "Ldbl": "1100000000",
    "RlpmAbamt": "1100000000"
}
```
### 3.3.4 잔액조회 Response Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---:|:---:|:---:|:---:|:---:|:---:|  
| Header || 공통부 |||||	 
| FinAcno |	핀-어카운트 |	필드 |	30 |	필수 |	 
| Ldbl |	원장잔액 |	필드 |	15 |	필수 |	 
| RlpmAbamt |	실지급가능액 |	필드 |	15 |	필수 |

### 3.4.1 개인카드승인내역조회 Request example
```json
{
    "Header": {
        "ApiNm": "InquireCreditCardAuthorizationHistory",
        "Tsymd": "20191212",
        "Trtm": "112428",
        "Iscd": "000013",
        "FintechApsno": "001",
        "ApiSvcCd": "CardInfo",
        "IsTuno": "121233243254",
        "AccessToken": "10b74dd7f5f0f521ecdc7ade82f793bdfc119c3635d2e5303ae6aba0c93d4246"
    },
    "FinCard": "00829101234560000112345678919",
    "IousDsnc": "1",
    "Insymd": "20191105",
    "Ineymd": "20191109",
    "PageNo": "1",
    "Dmcnt": "15"
}
```
### 3.4.2 개인카드승인내역조회 Request Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	
| FinCard |	핀-카드 | 필드 |	30 |	필수 |	 
| IousDsnc |	국내외사용구분 |	필드 |	1 |	필수 |	1:국내 2:해외 테스트에서는 '1' 고정값으로 입력 |
| Insymd |	조회시작일자 |	필드 |	8 |	필수 |	최고1년 테스트에서는 '20191105' 고정값으로 입력 |
| Ineymd |	조회종료일자 |	필드 |	8 |	- |	조회기간:최대3개월 테스트에서는 '20191109' 고정값으로 입력 |
| PageNo |	페이지번호 |	필드 |	4 |	- |	default : 1 조회건수 15건 초과하는 경우 (페이지번호 + 1)하여 연속거래 수행 테스트에서는 '1' 고정값으로 입력 |
| Dmcnt |	요청건수 |	필드 |	10 |	필수 |	최대 요청건수 15건 - 페이지당 건수 테스트에서는 '15' 고정값으로 입력 |
### 3.4.3 개인카드승인내역조회 Response example
```json
{
    "Header":{
        "ApiNm":"InquireCorporationCardAuthorizationHistory",
        "Tsymd":"20151014",
        "Trtm":"111045",
        "Iscd":"000013",
        "FintechApsno":"001",
        "ApiSvcCd":"CardInfo",
        "IsTuno":"201510140000000001",
        "Rpcd":"00000",
        "Rsms ":"정상처리되었습니다"},
        "PageNo":"1",
        "Dmcnt":"3",
        "CtntDataYn":"N",
        "TotCnt":"3",
        "Iqtcnt":"3"
        "REC":[{
        "CardAthzNo":"40927800",
        "Trdd":"20191105",
        "Txtm":"154038",
        "Usam":"100",
        "AfstNoBrno":"2936400278",
        "AfstNo":"146862942",
        "AfstNm":"핀테크상사",
        "AmslKnd":"1",
        "Tris":"00",
        "Ccyn":"0",
        "CnclYmd":"",
        "Crcd":"",
        "AcplUsam":""
        },{
        "CardAthzNo":"40927902",
        "Trdd":"20191105",
        "Txtm":"153837",
        "Usam":"100",
        "AfstNoBrno":"2936400278",
        "AfstNo":"146862942",
        "AfstNm":"박찬늘",
        "AmslKnd":"1",
        "Tris":"00",
        "Ccyn":"0",
        "CnclYmd":"",
        "Crcd":"",
        "AcplUsam":""
        },{
        "CardAthzNo":"41111115",
        "Trdd":"20191109",
        "Txtm":"182000",
        "Usam":"6000",
        "AfstNoBrno":"2936400283",
        "AfstNo":"146862947",
        "AfstNm":"할머니국밥",
        "AmslKnd":"1",
        "Tris":"00",
        "Ccyn":"0",
        "CnclYmd":"",
        "Crcd":"",
        "AcplUsam":""
}]}
```
### 3.4.4 개인카드승인내역조회 Response Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	 
| TotCnt |	총건수 |	필드 |	10 |	필수 |	 
| Iqtcnt |	조회총건수 |	필드 |	10 |	필수 |	 
| REC |	거래내역목록 |	반복부 | 필수 |	최대 15건 |
| CardAthzNo |	카드승인번호 |	필드 |	20 |	필수 |	 
| Trdd |	거래일자 |	필드 |	8 |	필수 |	 
|Txtm |	거래시각 |	필드 |	6 |	필수 |	 
| Usam |	이용금액 |	필드 |	19 |	필수 |	 
| AfstNoBrno |	가맹점사업자등록번호 |	필드 |	10 |	필수  |	 
| AfstNo |	가맹점번호 |	필드 |	20 |	필수 |	 
| AfstNm |	가맹점명 |	필드 |	50 |	필수 |	 
| AmslKnd |	매출종류 |	필드 |	1 |	필수 |	1:일시불 2:할부 3:현금서비스 6:해외일시불 7:해외할부 8:해외현금서비스 |
| Tris |	할부기간 |	필드 |	2 |	필수 |	 
| Ccyn |	취소여부 |	필드 |	1 |	- |	정상:0, 취소:1 |
| CnclYmd |	취소일자 |	필드 |	8 |	- |	취소시 취소일자 |
| Crcd |	통화코드 |	필드 |	3 |	- |	해외사용분 통화코드 |
| AcplUsam |	현지이용금액 |	필드 |	19 |	- | |	 
