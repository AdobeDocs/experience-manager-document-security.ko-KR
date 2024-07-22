---
title: Microsoft&reg; Office용 AEM Document Security Extension 사용
description: 아무리 널리 배포하더라도 수신자가 정책으로 보호된 파일을 사용하는 방법을 제어할 수 있습니다. 이 문서는 파일을 보호하는 방법과 보호된 파일로 작업하는 방법을 설명합니다.
uuid: db4abbc8-eb21-4f4a-9950-224ada95ce66
content-type: reference
topic-tags: using
discoiquuid: f4c2460c-174f-4e4d-b804-1eb051d2781e
exl-id: 667a9718-b865-4911-96c2-7c08f75e0732
source-git-commit: 6cf19ed9439e5be5a4c2e2fa2458879f37c25b96
workflow-type: tm+mt
source-wordcount: '6136'
ht-degree: 70%

---

# Microsoft® Office용 AEM Document Security Extension 사용{#using-aem-document-security-extension-for-microsoft-office}

## AEM Document Security Extension을 사용하여 파일 보호 {#usingaemdocumentsecurityextensiontoprotectfiles}

아무리 널리 배포하더라도 수신자가 정책으로 보호된 파일을 사용하는 방법을 제어할 수 있습니다.

Microsoft® Office용 Document Security Extension을 사용하여 다음 작업을 수행할 수 있습니다.

* Document Security에 대한 연결 구성
* 파일에 정책 적용
* Document Security 웹 페이지를 열어 사용자 정책 만들기 및 관리
* 파일에서 정책 보호 제거
* 파일에 적용되는 정책 변경
* Document Security 웹 페이지를 열어 파일에 대한 액세스 취소 또는 파일에 대한 정책 변경
* Document Security 웹 페이지를 열어 파일의 감사 기록 보기

### Document Security 서버에 연결 {#connect-to-a-document-security-server}

파일에 정책을 적용하려면 Document Security에 대한 연결 설정을 구성해야 합니다. Microsoft® Office용 Document Security Extension이 설치된 방법에 따라 기본 연결 설정이 이미 있을 수 있습니다. 하나 이상의 Document Security 인스턴스에 대한 연결 설정을 추가할 수 있습니다. Document Security 관리자로부터 서버 정보를 얻을 수 있습니다.

파일을 보호하거나 보호된 파일을 관리하는 데 사용할 서버를 기본 서버로 설정합니다. 새 파일에 정책을 적용하거나 Document Security 웹 페이지를 열면 Microsoft® Office용 Document Security Extension이 기본 서버에 연결됩니다. 둘 이상의 Document Security 인스턴스를 사용하여 파일을 보호하는 경우 서버 간 전환할 때 기본 서버 설정을 변경해야 합니다. 파일을 열 수 있는 권한이 있는 한 문서 보안 인스턴스로 보호되는 파일을 열 수 있습니다.

Document Security 서버가 인증서 기반 인증을 사용하는 경우 로컬 컴퓨터에서 받은 인증서를 설치해야 합니다. 인증서 인증을 선택하고 인증에 사용할 인증서를 제공해야 합니다.

하나의 Microsoft® Office 애플리케이션에서 Document Security 인스턴스에 대한 연결 설정을 구성하면 모든 Word, Excel 및 PowerPoint에 대해 구성됩니다.

#### 클라이언트측 인증서 설치 {#install-the-client-side-certificate}

인증서 인증 또는 양방향 인증을 통해 Document Security 웹 페이지에 액세스해야 하는 경우 로컬 컴퓨터에 설치해야 하는 인증서를 받게 됩니다. 인증서 파일(.PFX 또는 .P12 파일)과 해당 암호를 받습니다.

1. 로컬 컴퓨터에 인증서 파일을 저장합니다.
1. 인증서 파일을 더블 클릭하여 인증서 가져오기 마법사를 열고 **다음**&#x200B;을 클릭합니다.
1. 인증서 파일이 파일 이름 상자에 나열되면 **다음**&#x200B;을 클릭합니다. 다른 인증서를 찾으려면 **찾아보기**&#x200B;를 클릭합니다.
1. 받은 암호를 입력하고 **다음**&#x200B;을 클릭합니다.
1. 인증서 저장소 대화 상자에서 모든 인증서를 다음 저장소에 저장을 선택하고 **찾아보기**&#x200B;를 클릭합니다.
1. 인증서 저장소 선택 대화 상자에서 개인을 선택하고 **확인**&#x200B;을 클릭하고 **다음**&#x200B;을 클릭한 다음 **마침**&#x200B;을 클릭합니다.

#### 연결 설정 구성 {#configure-connection-settings}

1. Microsoft® Office 2010 및 Office 2013용 Document Security Extension의 **Document Security** 탭에서 **서버 선택**&#x200B;을 선택합니다.
1. **새로 만들기**&#x200B;를 클릭하여 연결 설정을 생성하거나 기존 연결을 선택하고 **편집**&#x200B;을 클릭합니다.
1. **이름** 상자에 연결 이름을 입력합니다. 어떤 이름이든 사용할 수 있습니다.
1. **서버 주소** 상자에 서버 주소를 입력합니다.
1. **포트** 상자에 서버 포트를 입력합니다.
1. (선택 사항) 사용자 이름과 암호를 기억하려면 **이 컴퓨터에 암호 저장**&#x200B;를 선택하고 해당 상자에 사용자 이름과 암호를 입력합니다. 다른 사람이 컴퓨터에 액세스할 수 있는 경우 이 옵션을 선택하지 않는 것이 좋습니다.
1. **이 서버에 연결**&#x200B;을 클릭합니다. Microsoft® Office용 Document Security Extension은 지정한 서버에 연결을 시도합니다. 지정된 인증 유형에 따라 다음 중 하나를 수행하십시오.

   **사용자 이름 및 암호**

   Document Security 관리자로부터 받은 사용자 이름과 암호를 입력합니다.

   **인증서 인증**

   개인 인증서 저장소에서 받아서 설치한 인증서를 선택하려면 이 옵션을 선택하십시오.

   Document Security에 하나의 인증 유형만 구성된 경우 해당 옵션만 나타납니다.

>[!NOTE]
>
>서버에 연결할 수 없는 경우 Internet Explorer에서 Document Security 웹 페이지를 열어 보십시오. Internet Explorer를 사용하여 서버에 연결할 수 없거나 대화 상자에 서버 인증서에 대한 경고가 표시되면 Microsoft® Office용 Document Security Extension이 서버에 연결할 수 없습니다. 도움이 필요하면 서버 관리자에게 문의하십시오.

>[!NOTE]
>
>Document Security에 연결할 수 없는 경우 &quot;사용자 이름과 암호가 올바르지 않습니다. 구성 설정을 확인하고 다시 시도하십시오.&quot;라는 메시지가 나타납니다. 다른 이유로 연결할 수 없는 경우 이 메시지가 나타날 수 있습니다. 처음으로 서버에 연결하는 경우 서버 이름과 포트를 올바르게 설정했는지 확인하십시오.

#### 기본 서버 지정 {#specify-the-default-server}

1. 다음 작업을 수행합니다.

   * Microsoft® Office 2010 및 Office 2013용 Document Security Extension의 **Document Security** 탭에서 **서버 선택**&#x200B;을 선택합니다.

1. 기본값으로 지정할 서버를 선택하고 **기본값 설정**&#x200B;을 클릭합니다. 기본 서버 옆에 별표가 나타납니다.

### 서드파티 인증 공급자 사용 {#using-third-party-authentication-providers}

AEM Forms Document Security와 함께 서드파티 인증 공급자를 사용할 수 있습니다. 이러한 인증 공급자는 보호된 문서에 추가 액세스 계층을 추가하는 데 도움이 됩니다. AEM Forms Document Security는 다음과 같은 확장 인증 워크플로를 지원합니다.

* 기본 AEM Forms URL을 사용한 확장 인증
* 사용자 지정 URL을 사용한 확장 인증
* JEE 서버의 AEM Forms에 구성된 서드파티 ID 공급자를 사용하는 기본 확장 인증 워크플로
* JEE 서버의 AEM Forms에 구성된 서드파티 ID 공급자를 사용하는 사용자 지정 확장 인증 워크플로
* SAML 인증을 나열하기 위해 사용자 지정된 페이지를 사용한 확장 인증

#### 기본 AEM Forms URL을 사용한 확장 인증 {#extended-authentication-using-default-aem-forms-url}

확장 인증에 기본 AEM Forms URL을 사용할 수 있습니다. 기본 랜딩 페이지에는 Adobe 브랜딩이 포함되어 있습니다. 또한 확장 인증에 기본 AEM Forms URL을 사용할 때 기본 AEM Forms 설정이 사용됩니다.

기본 Adobe 랜딩 URL을 사용한 확장 인증을 활성화하려면 다음 단계를 수행하십시오.

1. AEM Forms 관리자 UI를 엽니다.
1. 서비스 > 문서 보안 > 구성 > 서버 구성으로 이동합니다.
1. 확장 인증 허용 옵션을 활성화합니다.
1. 기본 URL 확장 인증 랜딩 URL을 지정합니다. 기본 URL은 http://localhost:8080/edc/extendedauthentication/welcome.jsp입니다.

   **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

   >[!NOTE]
   >
   >URL에 정규화된 이름을 사용하십시오. Adobe은 HTTPS 프로토콜을 사용할 것을 권장합니다.

   이제 AEM Forms Document Security는 기본 AEM Forms 랜딩 URL을 사용한 확장 인증을 사용하도록 구성됩니다.

   ![](assets/third-party-authentication.png)

#### 사용자 지정 랜딩 URL을 사용한 확장 인증 {#extended-authentication-with-a-custom-landing-url}

확장 인증에 사용자 지정 URL을 사용할 수 있습니다. 사용자 지정 브랜딩으로 사용자 지정 인증 페이지를 표시하는 유연성을 제공합니다. 예: 조직의 브랜딩.

사용자 지정 인증 페이지를 war 파일로 패키징하고 war 파일을 AEM Forms 서버에 배포할 수 있습니다. war 파일에는 사용자 자격 증명을 수락하고 AEM Forms 서버에 대해 인증하기 위한 완전한 논리가 포함되어 있습니다. AEM Forms Document Security에는 사용자 지정 인증 페이지에 대한 다음 요구 사항이 있습니다.

* 인증 페이지는 사용자 이름을 j_username으로, 암호를 j_password로 전송해야 합니다 페이지는 또한 source_url 및 login_url을 숨겨진 매개변수로 전송해야 합니다.
* 인증에 성공하면 페이지가 자동으로 닫힙니다.

사용자 지정 랜딩 URL을 사용한 확장 인증을 활성화하려면 다음과 같이 합니다.

1. 사용자 지정 인증 WAR 파일을 AEM Forms 서버에 배포합니다.
1. AEM Forms 관리자 UI를 엽니다.
1. 서비스 > 문서 보안 > 구성 > 서버 구성으로 이동합니다.
1. 확장 인증 허용 옵션을 활성화하고 사용자 지정 확장 인증 랜딩 URL을 지정합니다.
1. 항목 *&lt;node name=&quot;AllowedUrls&quot;>* 뒤에 SSO 노드의 `config.xml` 파일에 다음 항목을 추가하십시오.

   >[!NOTE]
   >
   >&lt;entry key=&quot;sso-l&quot; value=&quot;/ sample_/login.jsp&quot;/>`!!discoiqbr!!`&lt;entry key=&quot;sso-s&quot; value=&quot;/ sample_/welcome.jsp&quot;>`!!discoiqbr!!`&lt;entry key=&quot;sso-o&quot; value=&quot;/ sample_/logout.jsp&quot;/>`!!discoiqbr!!`

   onfig.xml 파일 업데이트에 대한 단계별 정보는 [문서 보안 구성 파일 수동 편집](https://experienceleague.adobe.com/en/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions#manually_editing_the_document_security_configuration_file)을 참조하십시오.

   이제 AEM Forms 문서 보안은 사용자 지정 랜딩 URL을 사용한 확장 인증을 사용하도록 구성됩니다.

#### AEM Forms 서버에 구성된 서드파티 ID 공급자를 사용하는 기본 확장 인증 워크플로 {#default-extended-authentication-workflow-with-third-party-identity-providers-configured-on-aem-forms-server}

확장 인증은 AEM Forms 서버에서 사용 가능한 다양한 유형의 인증을 사용할 수 있습니다. 예: SAML, [더 많은 예제는 무엇인가].

참고: SAML 공급자가 AEM Forms 서버에 구성된 경우 랜딩 URL을 표시하기 전에 SAML 인증을 위해 구성된 모든 ID 공급자가 포함된 페이지가 표시됩니다.

Acrobat에서 보호된 문서를 열면 다음 화면이 표시됩니다.

#### SAML 공급자가 AEM Forms 서버에 구성된 경우 사용자 지정 확장 인증 워크플로 {#custom-extended-authentication-workflow-when-saml-providers-are-configured-on-aem-forms-server}

SAML 공급자가 AEM Forms 서버에 구성된 경우 랜딩 URL을 표시하기 전에 SAML 인증을 위해 구성된 모든 ID 공급자가 포함된 페이지가 표시됩니다.

SAML 공급자가 AEM Forms 서버에 구성된 경우 사용자 지정 확장 인증 워크플로를 구성하기 위한 필수 조건은 다음과 같습니다.

* SAML 인증이 AEM Forms 서버에서 구성되어 있습니다.
* 사용자 지정 인증 페이지를 포함하며 사용자 자격 증명을 수락하고 AEM Forms 서버에 대해 인증하기 위한 완전한 논리를 포함하는 사용자 지정 war이 AEM Forms 서버에 배포됩니다.

#### SAML 인증을 나열하기 위해 사용자 지정 페이지 사용 {#using-custom-page-for-listing-saml-authentications}

AEM Forms 서버에 구성된 모든 인증 공급자를 포함하는 사용자 지정 페이지를 표시할 수도 있습니다 이러한 페이지를 만들려면 다음과 같이 합니다.

1. 사용자 지정 인증 페이지를 war 파일로 패키징하고 war 파일을 AEM Forms 서버에 배포합니다. war 파일에는 사용자 자격 증명을 수락하고 AEM Forms 서버에 대해 인증하기 위한 완전한 논리가 포함되어 있습니다.
1. AEM Forms 관리자 UI를 열고 **[!UICONTROL 설정]**> **[!UICONTROL 사용자 관리]** > **[!UICONTROL 구성]** > **[!UICONTROL SAML 서비스 공급자 설정]**&#x200B;으로 이동합니다.
1. 사용자 지정 속성 필드에 다음을 추가하고 **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

   *saml.sp.discovery.url=/demoJSP/saml_discovery.jsp*

   이제 AEM Forms Document Security가 구성된 모든 인증 공급자가 포함된 사용자 지정 페이지를 표시하도록 구성되었습니다.

### 사용자 계정 얻기 {#obtaining-a-user-account}

Document Security 계정이 아직 없는 경우 다음과 같은 이벤트가 발생할 때 Document Security에서 등록 프로세스를 시작할 수 있습니다.

* 정책으로 보호된 파일을 보내려는 Document Security 사용자가 귀하를 정책에 추가합니다.
* Document Security 관리자가 귀하의 계정을 생성합니다.

계정을 등록하고 활성화한 후에는 정책을 통해 사용 권한이 부여된 정책으로 보호된 파일을 사용할 수 있습니다.

>[!NOTE]
>
>정책으로 보호된 파일을 받았지만 Document Security 계정이 없는 경우 파일을 보낸 사람에게 도움을 요청하십시오. 마찬가지로, 등록 초대를 받은 경우 발신자에게 도움을 요청하십시오.

Document Security에서 이메일 등록 초대를 받은 경우 이메일의 URL을 사용하여 온라인 등록 페이지를 열어 등록할 수 있습니다. 등록 후 계정 활성화에 대한 두 번째 알림을 받게 됩니다.

#### 외부 사용자 계정 얻기 {#obtain-an-external-user-account}

1. Document Security 등록 이메일을 엽니다. 메시지에 포함된 URL은 Document Security 외부 사용자 등록 페이지에 대한 링크입니다. 등록 메시지를 받지 못한 경우 파일을 보낸 사람에게 도움을 요청하십시오.
1. URL을 클릭하거나 복사하여 브라우저에 붙여넣습니다.
1. 해당 상자에 이름, 조직 및 암호를 입력합니다. 아무 8자의 조합이 암호가 될 수 있습니다.

   >[!NOTE]
   >
   >기억하기 쉬운 암호를 선택하십시오. 잊어 버린 암호를 찾는 방법은 없습니다.

1. **등록**&#x200B;을 클릭합니다. 이메일에서 활성화 이메일 메시지를 확인하라는 메시지가 나타납니다.
1. Document Security 등록 확인 이메일을 엽니다.
1. 메시지에 나타나는 URL을 클릭합니다.
1. 로그인 페이지 링크를 클릭합니다.
1. **사용자 이름** 상자에 Document Security에 등록된 전자 메일 주소를 입력합니다. 이 이메일 주소는 기본 Document Security 사용자 이름입니다.
1. **암호** 상자에 등록할 때 생성한 암호를 입력합니다.
1. **로그인**&#x200B;을 클릭합니다.

### 정책 생성 및 관리 {#creating-and-managing-policies}

Document Security 관리자가 부여한 권한이 있는 경우 Document Security 웹 페이지의 정책 페이지에서 자신의 파일에 적용할 정책을 만들 수 있습니다.

Document Security 웹 페이지에서 정책을 만드는 데 사용할 수 있는 일부 정책 설정은 Word, Excel 및 PowerPoint 파일에서 지원되지 않습니다. 다음 표에서는 정책 권한이 Word, Excel 및 PowerPoint 기능에 매핑되는 방식을 설명합니다.

<table>
 <thead>
  <tr>
   <th><p>권한</p></th>
   <th><p>Word, Excel 및 PowerPoint 지원</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>인쇄 &gt; 허용되지 않음</p></td>
   <td><p>파일 인쇄가 허용되지 않습니다.</p></td>
  </tr>
  <tr>
   <td><p>인쇄 &gt; 허용됨</p></td>
   <td><p>파일 인쇄가 허용됩니다.</p><p><strong>참고</strong>: <i>정책에서 복사 권한은 제공하지만 인쇄 권한은 제공하지 않는 경우 다른 파일에 복사된 내용을 인쇄할 수 있습니다.</i></p></td>
  </tr>
  <tr>
   <td><p>인쇄&gt; 저해상도 전용</p></td>
   <td><p>해당 사항 없음</p></td>
  </tr>
  <tr>
   <td><p>변경 &gt; 모두</p></td>
   <td><p>파일을 변경할 수 있습니다.</p><p>이 권한이 주어지지 않으면 보호된 Word 및 Excel 파일을 수정할 수 없습니다. PowerPoint 파일은 수정할 수 있지만 변경 사항을 저장하거나 수정된 파일의 슬라이드 쇼를 볼 수는 없습니다.</p></td>
  </tr>
  <tr>
   <td><p>변경 &gt; 허용되지 않음</p></td>
   <td><p>사용자가 보호된 파일을 수정할 수 없습니다.</p></td>
  </tr>
  <tr>
   <td><p>변경 &gt; 페이지 변경</p></td>
   <td><p>해당 사항 없음</p><p>페이지 삽입, 삭제 및 회전이 포함됩니다.</p></td>
  </tr>
  <tr>
   <td><p>변경 &gt; 채우기 및 서명</p></td>
   <td><p>해당 사항 없음</p></td>
  </tr>
  <tr>
   <td><p>오프라인</p></td>
   <td><p>파일을 오프라인으로 열 수 있습니다.</p></td>
  </tr>
  <tr>
   <td><p>복사</p></td>
   <td><p>파일 내용을 다른 파일로 복사할 수 있습니다.</p></td>
  </tr>
  <tr>
   <td><p>스크린 리더 </p></td>
   <td><p>스크린 리더(시각 장애가 있는 사용자용 디바이스)가 파일 내용을 읽을 수 있습니다.</p></td>
  </tr>
  <tr>
   <td><p>권한 유효성</p></td>
   <td><p>지원됨</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>일반 설정</p></th>
   <th><p>Word, Excel 및 PowerPoint 지원</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>유효 기간</p></td>
   <td><p>지원됨</p></td>
  </tr>
  <tr>
   <td><p>감사 문서</p></td>
   <td><p>지원됨</p></td>
  </tr>
  <tr>
   <td><p>자동 오프라인 임대 기간</p></td>
   <td><p>지원됨</p></td>
  </tr>
  <tr>
   <td><p>외부 인증 공급자</p></td>
   <td><p>지원됨</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>고급 설정</p></th>
   <th><p>Word, Excel 및 PowerPoint 지원</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>동적 워터마크</p></td>
   <td><p>지원됨</p></td>
  </tr>
  <tr>
   <td><p>인증 플러그인</p></td>
   <td><p>해당 사항 없음</p></td>
  </tr>
  <tr>
   <td><p>암호화 알고리즘 및 키 길이 </p></td>
   <td><p>모든 옵션이 지원됩니다.</p></td>
  </tr>
  <tr>
   <td><p>문서 제한</p></td>
   <td><p>모든 파일 내용은 정책의 설정에 관계없이 항상 암호화됩니다.</p></td>
  </tr>
  <tr>
   <td><p>액세스 거부 오류 메시지</p></td>
   <td><p>지원됨</p></td>
  </tr>
 </tbody>
</table>

정책 생성 및 관리에 대한 자세한 내용은 [Document Security 최종 사용자 도움말](https://help.adobe.com/en_US/AEMForms/6.1/RMHelp/)을 참조하십시오.

### 정책 적용 {#applying-policies}

생성한 정책과 액세스 권한이 있는 정책 세트의 일부인 정책을 포함하여 사용 가능한 모든 정책을 파일에 적용할 수 있습니다. 정책을 적용하기 전에 파일을 저장해야 합니다.

정책을 적용하면 가장 자주 사용하는 정책을 보다 쉽게 적용할 수 있도록 AEM Document Security 메뉴의 최근 사용 목록에 추가됩니다. 최근 사용 목록에는 다른 Document Security 인스턴스에 로그인하지 않은 경우 연결된 서버 또는 기본 서버에 대한 정책만 표시됩니다.

>[!NOTE]
>
>정책은 Microsoft® Office 2010 및 2013의 Word(.doc, .docx, .docm), Excel(.xls, .xlsx, .xlsm) 및 PowerPoint(.ppt, .pptx, .pptm) 파일에만 적용할 수 있습니다. Word 템플릿 파일(.dot), Excel 템플릿 파일(.xlt) 및 PowerPoint 디자인 템플릿 파일(.pot)에는 정책을 적용할 수 없습니다.

#### 정책 적용 {#apply-a-policy}

1. Microsoft® Office 2010 및 2013용 Document Security Extension의 **Document Security** 탭에서 **보안 > 정책 선택**&#x200B;을 선택합니다.

   서버에서 사용자 이름과 암호를 인증 방법으로 선택하고 Document Security를 위한 로그인 정보를 아직 제공하지 않은 경우 사용자 이름과 암호를 묻는 대화 상자가 나타납니다.

1. 목록에서 정책을 선택하고 **적용**&#x200B;을 클릭합니다.
1. 파일을 저장합니다.

#### 최근에 사용한 정책 적용 {#apply-a-recently-used-policy}

1. Microsoft® Office 2010 및 2013용 Document Security Extension의 **Document Security** 탭에서 **보안** > *[정책 이름]*&#x200B;을 선택합니다.
1. 파일을 저장합니다.

## 정책으로 보호된 파일 작업 {#usingaemdocumentsecurityextensionpolicyprotectedfiles}

파일 게시자는 정책으로 보호된 파일의 지적 재산을 소유하며 Document Security가 이를 보호합니다.

파일 게시자 조직의 내부에 있든 외부에 있든 관계없이 정책으로 보호된 파일을 사용할 수 있습니다. 정책으로 보호된 파일을 열려면 Document Security가 사용자를 인식해야 합니다. LDAP/Active Directory를 통해 이루어져야 합니다. 또는 JEE의 LiveCycle/AEM 양식에 대한 로컬 사용자로 사용하거나 초대 후 등록해야 합니다.

정책으로 보호된 파일을 받았지만 Document Security 계정이 없는 경우 보낸 사람에게 도움을 요청하십시오. 마찬가지로, 등록 초대를 받은 경우 발신자에게 도움을 요청하십시오.

### Microsoft® Office에서 정책으로 보호된 파일 작업 {#working-with-policy-protected-files-in-microsoft-office}

Microsoft® Office용 Document Security Extension은 파일 게시자의 지적 재산을 보호하기 위해 특정 Word, Excel 및 PowerPoint 기능을 제한합니다. 파일을 변경할 수 있는 권한이 없으면 수정 사항을 저장할 수 없습니다.

정책으로 보호된 파일로 작업하는 경우 일부 제품 기능을 사용할 수 없거나 평소처럼 작동하지 않을 수 있습니다. 보호되지 않은 파일이 열려 있으면 복사 또는 내보내기 권한 없이 정책으로 보호된 파일에서 콘텐츠를 가져오거나 복사할 수 있는 기능을 제외한 대부분의 기능이 활성화됩니다.

>[!NOTE]
>
>Document Security Extension 지원 Office 애플리케이션을 사용하는 경우 Windows DEP 설정을 비활성화하는 것이 좋습니다. Document Security Extension과 실시간 검색이 활성화된 McAfee VirusScan이 있는 컴퓨터에서 Office 애플리케이션을 원활하게 시작하려면 McAfee VirusScan 콘솔에서 버퍼 오버플로 방지 옵션을 비활성화하십시오. 이러한 조정은 잠재적인 충돌을 방지하는 데 도움이 됩니다.

기능을 사용할 수 없는 경우 메뉴의 명령 이름과 관련 도구 모음 버튼을 사용할 수 없습니다. Microsoft® Office용 Document Security Extension에서 명령이나 단추 위에 마우스 포인터를 놓으면 Document Security에서 해당 명령을 사용할 수 없다는 도구 설명이 표시됩니다.

### 정책으로 보호된 파일 열기 {#opening-policy-protected-files}

다른 파일을 여는 데 사용하는 것과 동일한 방법을 사용하여 정책으로 보호된 파일을 열 수 있습니다. Document Security에 아직 로그인하지 않은 경우 로그인하라는 메시지가 표시됩니다. 즉, 인터넷에 연결되어 있지 않고 오프라인으로 파일을 열 수 있습니다. 로그인 프로세스를 취소하면 액세스가 거부됩니다.

파일을 열 수 있는 권한이 없는 경우 액세스가 거부되었다는 메시지가 표시됩니다. 파일 액세스 권한이 취소된 경우 업데이트된 파일 버전이 있는 경우 해당 버전으로 이동할 수도 있습니다. 정책으로 보호된 파일을 열 수 없는 경우 추가 지원이 필요하면 파일 게시자에게 문의하십시오.

보호된 파일이 열려 있을 때 파일 이름 뒤에 오는 제목 표시줄의 텍스트는 해당 파일이 AEM Document Security에 의해 보호되고 있음을 나타냅니다.

SharePoint Server로부터 Microsoft® Office용 Document Security Extension에서 보호된 문서를 열 때 Word, Excel 또는 PowerPoint와 같은 파일 형식과 연결된 Office 프로그램이 열려 있는지 확인하십시오. 관련 애플리케이션은 열지 않고 파일을 열려고 하면 문서가 열리지 않고 해당 플러그인을 설치해야 한다는 오류 메시지가 표시됩니다. Adobe 필요한 응용 프로그램을 열 뿐만 아니라 캐시 폴더를 지우는 것이 좋습니다. SharePoint 서버에서 Office용 Document Security Extension에서 보호된 문서를 열기 전에 이 작업을 수행하십시오. 또한 SharePoint Server로부터 보호된 문서를 열면 적용된 정책에 관계없이 문서에 대한 모든 권한이 비활성화됩니다.

Document Security에 구현된 인증 방법에 따라 보호된 문서를 열 때 인증 방법을 선택하라는 메시지가 표시될 수 있습니다. Document Security가 두 개 이상의 인증 방법을 지원하는 경우 인증 옵션이 표시됩니다. 예를 들어 Document Security 서버가 사용자 이름/암호 및 인증서 인증을 모두 제공하는 경우 적절한 인증 방법을 선택할 수 있습니다. 인증서 기반 인증이 활성화된 경우 받아서 설치한 인증서를 사용하라는 메시지가 표시됩니다.

보호된 파일을 열 때의 사용자 경험은 서버의 상호 인증 구성에 따라 다릅니다. 유효한 클라이언트 인증서가 하나만 설치된 경우 인증 대화 상자가 나타나지 않고 파일이 성공적으로 열립니다. 그러나 컴퓨터에 여러 클라이언트 인증서가 설치된 경우 인증 대화 상자가 나타납니다. 사용자는 보호된 파일을 열려면 유효한 인증서를 선택해야 합니다.

### 파일에서 정책 보호 제거 {#removing-policy-protection-from-a-file}

허용되는 경우 보호한 파일에서 정책 보호를 제거할 수 있습니다. 그렇게 하면 파일이 더 이상 Document Security에 의해 보호되지 않습니다.

1. Microsoft® Office 2010 및 2013용 Document Security Extension의 **Document Security** 탭에서 **제거**&#x200B;를 선택합니다.

   Document Security를 위한 로그인 정보를 아직 제공하지 않은 경우 사용자 이름과 암호를 묻는 대화 상자가 나타납니다.

>[!NOTE]
>
>보호 설정한 파일에서 정책을 제거할 수 없는 경우 문서 보안 관리자에게 문의하십시오.

### 보안 설정 보기 {#viewing-security-settings}

현재 파일에 대해 가지고 있는 인쇄 권한을 볼 수 있습니다. 파일 유효 기간과 더불어, 오프라인에서 복사, 변경 및 액세스할 때 현재 파일에 대한 권한을 볼 수도 있습니다.

Microsoft® Office 2010용 Document Security Extension에서는 Document Security 탭의 보안 상태 그룹에 파일에 대한 사용 권한이 표시됩니다.

다음 작업을 수행합니다.

* Microsoft® Office 2010 및 2013용 Document Security Extension의 **Document Security** 탭에서 **보안 상태** 그룹의 항목을 클릭합니다.

### 자동 적용 정책이 활성화된 경우 문서 저장 {#saving-documents-when-auto-apply-policy-is-enabled}

관리자가 자동 적용 정책 기능을 활성화한 경우 사용자가 만들거나 편집한 모든 문서는 문서를 저장할 때 자동으로 보호됩니다.

자동 적용 정책이 활성화된 경우 Microsoft® Office용 Document Security Extension은 Document Security 서버에 로그인하라는 메시지를 표시합니다. 서버에서 인증할 수 있도록 사용자 이름과 암호를 입력합니다. 올바른 로그인 자격 증명을 제공한 경우 문서가 저장되고 보호됩니다.

>[!NOTE]
>
>Document Security에 로그인할 수 없는 경우 문서가 저장될 수도, 저장되지 않을 수도 있습니다. 이 상황은 관리자가 자동 적용 정책을 구성한 방법에 따라 다릅니다. 이런 상황에서는 문서가 어떻게 처리되는지 관리자에게 문의하십시오.

### 오프라인 액세스를 위한 동기화 {#synchronizing-for-offline-access}

정책을 사용하면 오프라인 상태이며 문서 보안에 연결되지 않은 상태에서도 파일을 열 수 있습니다. 오프라인으로 작업하려면 이전에 Document Security에 로그인하여 서버에 대한 자격 증명을 설정해야 합니다. Adobe 오프라인으로 파일 작업을 계획하는 경우 Document Security와 동기화하는 것이 좋습니다. 연결을 끊기 전에 연결을 끊어 파일에 대한 정책 설정이 서버와 최신 상태인지 확인하십시오. Adobe 오프라인으로 열기 전에 온라인으로 한 번 파일을 여는 것이 좋습니다. 온라인으로 한 번 파일을 열지 않거나 서버와 동기화하지 않은 경우에도 오프라인 상태에서 정책으로 보호된 파일을 계속 사용할 수 있습니다. 단, 오프라인 임대 기간이 만료되지 않았어야 하며, 마지막으로 서버와 수동 또는 자동 동기화한 이후 파일에 대한 정책 설정이 변경되지 않았어야 합니다.

다음 작업을 수행합니다.

* Microsoft® Office 2010 및 Office 2013용 Document Security Extension의 **Document Security** 탭에서 **오프라인 동기화**&#x200B;을 선택합니다.

  ***참고&#x200B;**: 사용자에게 문서에 대한 오프라인 권한이 없는 경우에도 오프라인 동기화 단추를 사용할 수 있습니다. 그러나 버튼을 선택해도 아무 작업도 수행되지 않습니다.*

### 동적 워터마크 작업 {#working-with-dynamic-watermarks}

Microsoft® Office용 Document Security Extension은 정책으로 보호된 문서에 동적 텍스트 기반 워터마크를 포함하는 것을 지원합니다. 동적 워터마크에는 날짜, 시간, 사용자 이름 또는 정책 이름과 같이 변경될 수 있는 정보가 포함될 수 있습니다. 사용자가 정책으로 보호된 파일을 인쇄하고 해당 파일에 동적 워터마크와 인쇄 권한이 포함된 경우 워터마크가 출력에 나타납니다.

Document Security Extension은 풍부한 워터마크 기능을 지원하지 않습니다. 풍부한 워터마크 기능에는 PDF 기반 워터마크, 워터마크의 여러 요소, 텍스트 서식 옵션 등이 포함됩니다. 페이지 범위도 포함됩니다.

Document Security 웹 페이지를 사용하여 동적 워터마크를 만들 수 있습니다. 자세한 내용은 [Document Security 최종 사용자 도움말](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/forms/administrator-help/work-with-document-security/document-security)을 참조하십시오.

Microsoft® Office용 Document Security Extension은 다음과 같은 워터마크 기능을 지원합니다.

<table>
 <thead>
  <tr>
   <th><p>Document Security 워터마크 옵션</p></th>
   <th><p>Word, Excel 및 PowerPoint 지원</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>정책 이름</p></td>
   <td><p>지원됨</p></td>
  </tr>
  <tr>
   <td><p>워터마크 이름</p></td>
   <td><p>지원됨</p></td>
  </tr>
  <tr>
   <td><p>배경으로 사용</p></td>
   <td><p>동적 워터마크의 표시 동작은 배경으로 사용 선택 여부에 관계없이 동일합니다.</p><p>Word 2010 및 2013의 경우 동적 워터마크는 인쇄 레이아웃 및 인쇄 미리보기 보기에만 나타납니다. </p><p>Excel 2010 및 2013의 경우에도 인쇄 미리 보기 및 페이지 레이아웃 보기에 나타납니다.</p></td>
  </tr>
  <tr>
   <td><p>세로 위치</p></td>
   <td><p>지원됨</p></td>
  </tr>
  <tr>
   <td><p>가로 위치</p></td>
   <td><p>지원됨</p><p>Excel 2010 및 2013의 경우 포인트를 사용한 워터마크의 가로 위치가 작동하지 않습니다.</p></td>
  </tr>
  <tr>
   <td><p>크기 조정</p></td>
   <td><p>지원됨</p></td>
  </tr>
  <tr>
   <td><p>위치</p></td>
   <td><p>지원됨</p></td>
  </tr>
  <tr>
   <td><p>불투명도</p></td>
   <td><p>지원됨</p></td>
  </tr>
 </tbody>
</table>

### Document Security 웹 페이지 열기 {#opening-the-document-security-web-pages}

Document Security 웹 페이지를 열어 사용자 정책을 생성 및 업데이트하고 정책으로 보호된 파일에 대한 상태 및 감사 정보를 볼 수 있습니다. Document Security 웹 페이지를 사용하여 정책을 변경하거나 정책으로 보호된 파일에 대한 액세스를 취소할 수도 있습니다.

Document Security 웹 페이지를 열려면 Microsoft® Office 2010 및 2013용 Document Security Extension의 **Document Security** 탭에서 **정책 생성 및 관리**&#x200B;를 선택합니다. 로그인 정보를 아직 제공하지 않은 경우 브라우저에서 서버 로그인 페이지가 열립니다.

### 정책 변경 {#changing-policies}

일반적으로 Document Security 관리자 또는 파일 게시자와 같은 권한이 있는 경우 나중에 다른 정책을 파일에 적용하거나 현재 적용된 정책의 설정을 변경할 수 있습니다.

정책의 설정을 변경하려면 Document Security 웹 페이지를 사용하십시오.

1. 다음 작업을 수행합니다.

   * Microsoft® Office 2010 또는 2013용 Document Security Extension의 **Document Security** 탭에서 **보안 > 보안 변경**&#x200B;을 선택합니다.

1. 목록에서 정책을 선택하고 **적용**&#x200B;을 클릭합니다.

### 파일 액세스 권한 취소 {#revoking-file-access-privileges}

보호한 파일을 여는 기능을 취소할 수 있습니다. 파일 액세스를 취소할 때 사용자가 파일 액세스를 열려고 할 때 메시지를 지정하고 수정된 사본으로 바꿀 경우 업데이트된 버전에 대한 URL을 제공할 수 있습니다.

1. 다음 작업을 수행합니다.

   * Microsoft® Office 2010 및 2013용 Document Security Extension의 **Document Security** 탭에서 **취소**&#x200B;를 선택합니다.

   Document Security 웹 페이지가 문서 취소 페이지로 열립니다.

1. 표시할 메시지를 지정하고, 업데이트된 버전의 URL을 지정하고(사용 가능한 경우) **확인**&#x200B;을 클릭합니다.

파일 액세스 권한 취소에 대한 자세한 내용은 [Document Security 최종 사용자 도움말](https://help.adobe.com/en_US/AEMForms/6.1/RMHelp/)을 참조하십시오.

Document Security 웹 페이지를 통해 액세스 권한을 복원할 수 있습니다.

### 파일 감사 기록 보기 {#viewing-the-file-audit-history}

Document Security는 정책으로 보호된 파일에 대한 감사 기록을 저장하여 사용자가 파일에 대해 수행하는 작업을 감사할 수 있습니다.

Word, Excel 및 PowerPoint 파일에 대한 감사 이벤트는 다음과 같습니다.

**새 문서 보안** 정책이 파일에 적용됨

**문서 보기** 파일이 열림

**문서 닫기** 파일이 닫힘

**파일 취소** 파일에 대한 액세스 권한이 제거됨

**파일 해지 취소** 파일에 대한 액세스 권한이 반환됨

**문서 수정** 파일이 변경되고 로컬에 저장됨

**고해상도 인쇄** 파일이 인쇄됨

**보안 처리기 변경** 파일에서 정책 보호가 제거됨

**문서의 정책 전환** 새 정책이 문서 보안 웹 페이지의 파일에 적용됨

### 파일에 대한 감사 기록 보기 {#view-the-audit-history-for-a-file}

Microsoft® Office 2010 및 2013용 Document Security Extension의 **Document Security** 탭에서 **감사 기록**&#x200B;을 선택합니다.

Document Security 웹 페이지는 현재 파일에 대해 감사된 이벤트를 표시하는 이벤트 페이지로 열립니다.

### Microsoft® Office 제한 기능 {#microsoft-office-restricted-features}

지적 재산을 보호하기 위해 정책으로 보호된 파일이 열려 있으면 일부 Microsoft® Office 기능을 사용할 수 없습니다. 사용할 수 없는 기능 목록은 현재 사용자에게 부여된 권한에 따라 다릅니다. 보호된 세션에 있는 상태일 때 일부 기능은 보호된 파일에 대해서만 사용할 수 없고 다른 기능은 모든 파일에 대해 사용할 수 없습니다. 일반적으로 정책으로 보호된 파일을 열 때부터 애플리케이션을 닫거나 세션이 만료될 때까지 보호된 세션에 있는 상태입니다.

대부분의 정책은 파일 게시자에게 모든 권한을 부여합니다. 다른 사용자들은 추가적인 기능 제한을 의식하게 될 수 있습니다.

명령을 사용할 수 없는 경우 메뉴의 명령 이름과 관련 도구 모음 버튼이 회색으로 표시됩니다.

>[!NOTE]
>
>임베디드 파일에 대한 링크가 포함된 파일에 정책을 적용하면 링크된 파일에 정책이 적용되지 않습니다 Microsoft® Office용 Document Security는 링크된 파일에 대한 보호를 확장하지 않습니다.

* 정책으로 보호된 Word, Excel 및 PowerPoint 파일은 Internet Explorer 브라우저 창에서 열리지 않도록 차단됩니다.
* 변경 권한만 부여된 사용자는 Windows 클립보드를 사용하여 다른 애플리케이션에서 파일로 콘텐츠를 복사할 수 없습니다. 사용자는 Microsoft® Office 클립보드 옵션을 활성화하여 콘텐츠를 파일로 복사할 수 있습니다.
* Microsoft® Office에서 정책으로 보호된 파일을 열면 애플리케이션을 닫거나 세션이 만료될 때까지 Print Screen 키를 사용할 수 없습니다.
* Microsoft® Office용 Document Security는 WebDAV(Web-based Distributed Authoring and Versioning)를 지원하지 않습니다. 일반적으로 WebDAV 폴더에서 정책으로 보호된 파일을 열 수 없습니다. 정책으로 보호된 파일을 열 수 있는 경우 파일에서 저장, 인쇄, 변경 또는 복사할 수 있는 권한은 없습니다.

정책으로 보호된 파일에 적용되는 일반 보안에는 다음 제한 사항이 포함됩니다.

보호된 세션 중에는 Word, Excel 및 PowerPoint에서 많은 공통 기능이 제한될 수 있습니다.

사용자의 변경을 허용하지 않는 정책으로 보호된 파일이 열려 있으면 파일을 변경하는 명령을 사용할 수 없습니다. 문서를 열거나 만들고 애플리케이션 기본 설정을 변경하는 명령만 사용할 수 있습니다.

#### Word 2010 및 Word 2013 제한 사항 {#word-2010-and-word-2013-restrictions}

Word에서 정책으로 보호된 파일을 열면 Word를 닫고 다시 시작할 때까지 자동 파일 복구 정보를 저장할 수 없습니다. 또한 아래 나열된 기능은 설명된 상황에서 제한됩니다.

**파일 > 새로 만들기 > 기존 항목에서 새로 만들기** 사용 가능하지만 정책으로 보호된 파일이 열려 있는 동안에는 이 명령을 사용하여 생성된 파일은 저장할 수 없습니다. 새 파일의 내용은 다른 파일로 복사할 수 없습니다.

**파일 > 저장** 변경 권한에 의해 제한됩니다.

**파일> 다른 이름으로 저장** 모든 옵션은 변경 권한에 의해 제한됩니다.

**파일 > 인쇄** 모든 옵션은 인쇄 권한에 의해 제한됩니다. 정책에서 고해상도 인쇄가 허용되지 않는 한 사용할 수 없습니다.

**파일 > 저장 및 보내기** 보호된 세션 중에는 모든 옵션을 사용할 수 없습니다.

**파일 > 정보 > Protect 문서 > 암호 설정, 디지털 서명 추가, 최종본으로 표시, 사용자별로 권한 제한** 보호된 세션 중에는 사용할 수 없습니다.

**파일 > 워크플로** 보호된 세션 중에는 사용할 수 없습니다.

***참고&#x200B;**: Word, Excel 및 PowerPoint 2010에서 워크플로를 시작하는 방법은 Office Professional Plus 2010, Office Enterprise 2010, Office Ultimate 2010 및 독립 실행형 2010 버전에서만 사용할 수 있습니다.*

**블로그 게시물 > 게시** 보호된 세션 중에는 사용할 수 없습니다.

**파일 > 서버 > 파일 서버 작업 메뉴** 보호된 세션 중에는 사용할 수 없습니다.

**홈 > 클립보드 > 복사** 복사 권한에 의해 제한됩니다. 복사가 허용되지 않으면 복사된 콘텐츠를 다른 파일이나 Office 클립보드에 붙여넣을 수 없습니다. 사용자에게 변경 권한이 있는 경우 보호된 파일 내에서 콘텐츠를 복사할 수 있습니다.

**홈 > 클립보드 > 붙여넣기** 변경 권한에 의해 제한됩니다.

**홈 > 클립보드 > 선택하여 붙여넣기** 변경 권한에 의해 제한됩니다.

**삽입 > 텍스트 > 오브젝트** 보호된 세션 중에는 사용할 수 없습니다. 어느 때라도 정책으로 보호된 파일은 삽입할 수 없습니다.

**메일링** 보호된 세션 중에는 이 탭의 옵션 대부분을 사용할 수 없습니다.

**검토 > 교정 > 조사** 복사 권한에 의해 제한됩니다. 복사가 허용되지 않으면 사용할 수 없습니다.

**검토 > 교정 > 동의어 사전** 복사 권한에 의해 제한됩니다. 복사가 허용되지 않으면 사용할 수 없습니다.

**검토 > 언어 > 번역 > 문서 번역** 복사 권한으로 활성화됩니다.

**검토 > 언어 > 번역 > 선택한 텍스트 번역** 복사 권한으로 활성화됩니다.

**검토 > 언어 > 번역 > 미니 번역기** 복사 권한으로 활성화됩니다.

**검토 > 비교 > 비교** 보호된 세션 중에는 사용할 수 없습니다. 어느 때라도 정책으로 보호된 파일은 비교할 수 없습니다.

**검토 > 보호 > 작성자 차단** 보호된 세션 중에는 사용할 수 없습니다.

**검토 > 보호 > 편집 제한** 보호된 세션 중에는 사용할 수 없습니다.

**보기 > 매크로** 복사 권한은 일부 매크로를 제한하므로 복사가 허용되지 않는 한 사용할 수 없습니다.

**추가 기능** 보호된 세션 중에는 추가하거나 제거할 수 없습니다.

**온라인 공동 작업** 보호된 세션 중에는 사용할 수 없습니다.

**기본 및 하위 문서** 기본 문서 정책은 기본 문서 내에서 하위 문서를 열 때 하위 문서를 제어합니다. 별도로 열면 하위 문서를 인쇄하거나 복사하거나 수정할 수 없습니다.

**다시 요약** 보호된 세션 중에는 사용할 수 없습니다.

**프레임 (및 모든 관련 명령)** 보호된 세션 중에는 사용할 수 없습니다.

**문서 패널** 보호된 세션 중에는 사용할 수 없습니다.

**개발자 > 문서 템플릿** 보호된 세션 중에는 사용할 수 없습니다. 이 명령에 액세스하려면 파일 > 옵션 > 사용자 지정 > 개발자 탭 > 템플릿 > 문서 템플릿을 선택합니다.

**개요> 기본 문서 > 하위 문서 만들기, 하위 문서 삽입** 보호된 세션 중에는 사용할 수 없습니다.

#### Excel 2010 및 Excel 2013 제한 사항 {#excel-2010-and-excel-2013-restrictions}

아래 나열된 기능은 설명된 상황에서 제한됩니다.

**파일 > 새로 만들기 > 기존 항목에서 새로 만들기** 사용 가능하지만 보호된 세션 동안에는 이 명령을 사용하여 생성된 파일은 저장할 수 없습니다. 새 파일의 내용은 다른 파일로 복사할 수 없습니다.

**파일 > 저장, 다른 이름으로 저장** 변경 권한에 의해 제한됩니다.

**파일 > 다른 이름으로 저장 > PDF** 보호된 세션 중에는 사용할 수 없습니다.

**파일 > 인쇄** 인쇄 권한에 의해 제한됩니다. 정책에서 고해상도 인쇄가 허용되지 않는 한 사용할 수 없습니다.

**파일 > 정보 > 문서 보호** 보호된 세션 중에는 사용할 수 없습니다.

**파일 > 정보 > 통합 문서 보호** 보호된 세션 중에는 사용할 수 없습니다.

**파일 > 저장 및 보내기** 보호된 세션 중에는 사용할 수 없습니다.

**파일 > 옵션 > 추가 기능** 보호된 세션 중에는 추가하거나 제거할 수 없습니다.

**파일 > 워크플로** 보호된 세션 중에는 사용할 수 없습니다.

***참고&#x200B;**: Word, Excel 및 PowerPoint 2010에서 워크플로를 시작하는 방법은 Office Professional Plus 2010, Office Enterprise 2010, Office Ultimate 2010 및 독립 실행형 2010 버전에서만 사용할 수 있습니다.*

**파일 > 서버 > 파일 서버 작업 메뉴** 보호된 세션 중에는 사용할 수 없습니다.

**홈 > 클립보드 > 복사** 복사 권한에 의해 제한됩니다. 복사가 허용되지 않으면 복사된 콘텐츠를 다른 파일이나 Microsoft® Office 클립보드에 붙여넣을 수 없습니다. 사용자에게 변경 권한이 있는 경우 보호된 파일 내에서 콘텐츠를 복사할 수 있습니다.

**홈 > 클립보드 > 붙여넣기** 변경 권한에 의해 제한됩니다.

**홈 > 클립보드 > 선택하여 붙여넣기** 변경 권한에 의해 제한됩니다.

**홈 > 셀 > 서식 > 시트 이동 또는 복사** 보호된 세션 중에는 사용할 수 없습니다.

**홈 > 셀 > 삽입 > 시트 삽입** 보호된 세션 중에는 사용할 수 없습니다.

**홈 > 셀 > 삭제 > 시트 삭제** 보호된 세션 중에는 사용할 수 없습니다.

**홈 > 편집 > 채우기 > 워크 시트 전체** 변경 권한에 의해 제한됩니다.

**삽입 > 테이블 > 테이블** 변경 권한에 의해 제한됩니다.

**삽입 > 테이블 > 피벗 테이블** 정책으로 보호된 파일은 생성 마법사에서 선택할 수 없습니다.

**삽입 > 텍스트 > 오브젝트** 보호된 세션 중에는 사용할 수 없습니다. 어느 때라도 정책으로 보호된 파일은 삽입할 수 없습니다.

**삽입 > 텍스트 > 머리글 및 바닥글** 변경 권한에 의해 제한됩니다. 정책으로 보호된 문서에는 사용할 수 없습니다.

**데이터 > 외부 데이터 가져오기** 정책으로 보호된 파일에서 데이터를 가져올 수 없습니다.

**파일 > 개요 > 부분합** 변경 권한에 의해 제한됩니다.

**파일 > 데이터 도구 > 데이터 유효성** 변경 권한에 의해 제한됩니다.

**검토 > 교정 > 조사** 복사 권한에 의해 제한됩니다.

**검토 > 교정 > 동의어 사전** 복사 권한에 의해 제한됩니다.

**검토 > 언어 > 번역** 복사 권한에 의해 제한됩니다.

**검토 > 변경 내용 > 시트 보호** 보호된 세션 중에는 사용할 수 없습니다.

**검토 > 변경 내용 > 통합 문서 보호** 보호된 세션 중에는 사용할 수 없습니다.

**검토 > 변경 내용 > 통합 문서 공유** 보호된 세션 중에는 사용할 수 없습니다.

**검토 > 변경 내용 > 통합 문서 보호 및 공유** 보호된 세션 중에는 사용할 수 없습니다.

**검토 > 변경 내용 > 범위 편집 허용** 보호된 세션 중에는 사용할 수 없습니다.

**검토 > 변경 내용 > 변경 내용 추적 > 변경 내용 강조 표시** 동적 워터마크가 포함된 정책 보호 파일에는 사용할 수 없습니다.

**보기 > 매크로** 변경 권한에 의해 제한됩니다.

**보기 > 작업 영역 저장** 명령이 작동하지 않습니다.

**개발자 > XML > 확장 팩** 복사 권한은 일부 매크로를 제한하므로 복사를 허용하지 않는 한 사용할 수 없습니다.

**수식 > 수식 감사 > 오류 검사** 변경 권한에 의해 제한됩니다. 변경이 허용되지 않는 한 사용할 수 없습니다.

**온라인 공동 작업** 보호된 세션 중에는 사용할 수 없습니다.

**자동 복구 정보 저장** 보호된 세션 중에는 사용할 수 없습니다.

***참고&#x200B;**: 권한이 없는 정책으로 보호된 파일의 셀을 변경하려고 하면 Excel에서 시트 보호 해제 명령을 사용하여 보호를 제거하라는 경고가 잘못 표시됩니다.*

#### PowerPoint 2010 및 PowerPoint 2013 제한 사항 {#powerpoint-2010-and-powerpoint-2013-restrictions}

아래 나열된 기능은 설명된 상황에서 제한됩니다.

**파일 > 새로 만들기 > 기존 항목에서 새로 만들기** 사용 가능하지만 보호된 세션 동안에는 이 명령을 사용하여 생성된 파일은 저장할 수 없습니다. 새 파일의 내용은 다른 파일로 복사할 수 없습니다.

**파일 > 저장** 변경 권한에 의해 제한됩니다.

**파일> 다른 이름으로 저장** 모든 옵션은 변경 권한에 의해 제한됩니다.

**파일 > 인쇄** 모든 옵션은 인쇄 권한에 의해 제한됩니다. 정책에서 고해상도 인쇄가 허용되지 않는 한 사용할 수 없습니다.

**파일 > 저장 및 보내기** 보호된 세션 중에는 사용할 수 없습니다.

**파일 > 정보 > Protect 프레젠테이션 > 암호 설정, 디지털 서명 추가, 최종본으로 표시, 사용자별로 권한 제한** 보호된 세션 중에는 사용할 수 없습니다.

**파일 > PowerPoint 옵션 > 자동 복구 정보 저장** 보호된 세션 중에는 사용할 수 없습니다.

**파일 > 서버 > 파일 서버 작업 메뉴** 보호된 세션 중에는 사용할 수 없습니다.

**홈 > 클립보드 > 복사** 복사 권한에 의해 제한됩니다. 복사가 허용되지 않으면 복사된 내용을 문서 내에 또는 다른 파일에 또는 Office 클립보드에 붙여넣을 수 없습니다. 사용자에게 변경 권한이 있는 경우 보호된 파일 내에서 콘텐츠를 복사할 수 있습니다.

**홈 > 클립보드 > 붙여넣기** 변경 권한에 의해 제한됩니다. 복사가 허용되지 않으면 복사된 내용을 문서 내에 붙여넣을 수 없습니다.

**홈 > 클립보드 > 선택하여 붙여넣기** 변경 권한에 의해 제한됩니다.

**홈 > 슬라이드 > 새 슬라이드 > 개요에서 슬라이드 삽입, 슬라이드 재사용** 보호된 세션 중에는 사용할 수 없습니다.

**삽입 > 텍스트 > 오브젝트** 보호된 세션 중에는 사용할 수 없습니다. 어느 때라도 정책으로 보호된 파일은 삽입할 수 없습니다.

**디자인 > 배경 > 배경 스타일, 배경 그래픽 숨기기, 배경 서식** 동적 워터마크가 포함된 정책 보호 파일에는 사용할 수 없습니다.

**슬라이드 쇼 > 설정 > 슬라이드 쇼 녹화** 변경 권한에 의해 제한됩니다.

**검토 > 교정 > 동의어 사전** 복사 권한에 의해 제한됩니다.

**검토 > 언어 > 번역** 복사 권한에 의해 제한됩니다.

**검토 > 언어 > 번역 > 미니 번역기** 복사 권한으로 활성화됩니다.

**보기 > 프레젠테이션 보기> 슬라이드 쇼** 변경 권한에 의해 제한됩니다. 변경이 허용되지 않는 경우 파일이 수정되면 슬라이드 쇼를 볼 수 없습니다.

**보기 > 매크로** 복사 권한은 일부 매크로를 제한하므로 복사가 허용되지 않는 한 사용할 수 없습니다.

**추가 기능** 보호된 세션 중에는 추가하거나 제거할 수 없습니다.

**온라인 공동 작업** 보호된 세션 중에는 사용할 수 없습니다.

## 서드파티 인증 공급자 사용 {#use-third-party-authentication-providers}

AEM Forms Document Security와 함께 서드파티 인증 공급자를 사용할 수 있습니다. 이러한 인증 공급자는 보호된 문서에 추가 액세스 계층을 추가하는 데 도움이 됩니다. AEM Forms Document Security는 다음과 같은 확장 인증 워크플로를 지원합니다.

* 기본 AEM Forms URL을 사용한 확장 인증
* 사용자 지정 URL을 사용한 확장 인증
* JEE 서버의 AEM Forms에 구성된 서드파티 ID 공급자를 사용하는 기본 확장 인증 워크플로
* JEE 서버의 AEM Forms에 구성된 서드파티 ID 공급자를 사용하는 사용자 지정 확장 인증 워크플로
* SAML 인증을 나열하기 위해 사용자 지정된 페이지를 사용한 확장 인증

## 용어 설명 {#glossary}

JEE 용어에 대한 LiveCycle 및 AEM Forms에 대한 자세한 내용은 [19장: 용어집](https://helpx.adobe.com/content/dam/help/en/experience-manager/6-5/forms/pdf/using-designer.pdf)을 참조하십시오.
