## 필수 구성 요소
```
ISO-10303-21; >> 파일 시작 선언
HEADER; >> 헤더 섹션
ENDSEC;
DATA; >> 데이터 섹션
ENDSEC;
END-ISO-10303-21; >> 파일 종료 선언
```
</br>
</br>
## HEADER SECTION
- 데이터 필드 time_stamp 그리고 FILE_SCHEMA 를 제외한 모든 필드에는 빈 문자열이 포함될 수 있음.
```
HEADER;
FILE_DESCRIPTION(
/* description */ (' '),
/* implementation_level */ '2;1'); >> 이 파일의 버전 및 적합성 옵션.

FILE_NAME(
/* name */ 'demo',
/* time_stamp */ '2003-12-27T11:57:53', >> 시간 표현 : ISO 8601
/* author */ (' '), >> 작성자
/* organization */ (' '), >> 조직 이름
/* preprocessor_version */ ' ', >> 이 파일을 생성하는 시스템의 이름과 버전
/* originating_system */ ' ', >> 이 Step 파일에 포함된 정보를 원래 만든 시스템의 이름과 버전
/* authorization */ ' '); >> 이 파일을 승인한 사람의 이름과 우편주소

FILE_SCHEMA (('AUTOMOTIVE_DESIGN { 1 0 10303 214 2 1 1}')); >> DATA section 의 정보를 제어하는 하나 이상의 Express 스키마
ENDSEC;
```
</br>
</br>
## DATA SECTION
```
DATA;
#10=ORGANIZATION('O0001','LKSoft','company');
#11=PRODUCT_DEFINITION_CONTEXT('part definition',#12,'manufacturing');
#12=APPLICATION_CONTEXT('mechanical design');
#13=APPLICATION_PROTOCOL_DEFINITION('','automotive_design',2003,#12);
#14=PRODUCT_DEFINITION('0',$,#15,#11);
#15=PRODUCT_DEFINITION_FORMATION('1',$,#16);
#16=PRODUCT('A0001','Test Part 1','',(#18));
#17=PRODUCT_RELATED_PRODUCT_CATEGORY('part',$,(#16));
#18=PRODUCT_CONTEXT('',#12,'');
#19=APPLIED_ORGANIZATION_ASSIGNMENT(#10,#20,(#16));
#20=ORGANIZATION_ROLE('id owner');
ENDSEC;
```
- 인스턴스 이름 : 
  - 모든 엔터티 인스턴스는 "#1234" 형식의 고유한 이름을 갖는다.
  - 인스턴스 이름은 양수로( > 0 )로 구성되어야 하며, 일반적으로 2 보다 작다.
  - 인스턴스 이름은 step 파일 내에서만 로컬로 유효하다.
  - 동일한 콘텐츠를 시스템에서 다시 내보내는 경우 동일한 인스턴스에 대해 인스턴스 이름이 다를 수 있다.
  - 인스턴스 이름은 속성 값이나 집계 멤버를 통해 다른 엔티티의 인스턴스를 참조하는데에도 사용된다, 참조된 인스턴스는 현재 인스턴스의 앞이나 뒤에 정의될 수 있다.
</br>
</br>
---

<a> https://en.wikipedia.org/wiki/ISO_10303-21  
<a> https://www.steptools.com/stds/step/IS_final_p21e3.html  
<a> https://www.loc.gov/preservation/digital/formats/fdd/fdd000448.shtml  

