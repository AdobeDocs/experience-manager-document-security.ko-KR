---
title: Microsoft Office용 AEM Document Security Extension 설치 및 구성
description: 이 문서는 Microsoft Office용 Adobe Experience Manager Document Security Extension 6.2를 설치하고 구성하는 과정을 안내합니다.
uuid: 9d7eb6bb-4780-4d82-8657-7c6c6d523af0
content-type: reference
topic-tags: installing
discoiquuid: f1cdf344-efe4-4cb5-9fc3-47ee4ba5faf4
exl-id: 88759737-d57f-4354-951e-ad9f62d0a872
source-git-commit: 3b6a686966fb8d006bed8cc4a4bf5eebe0dfb030
workflow-type: tm+mt
source-wordcount: '2821'
ht-degree: 66%

---

# Microsoft Office용 AEM Document Security Extension 설치 및 구성{#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

이 문서에서는 Microsoft Office용 Adobe Experience Manager Document Security Extension을 설치 및 구성하는 과정을 안내합니다.

이 문서에는 다음 작업에 대한 정보가 포함되어 있습니다.

* Microsoft Office용 Document Security Extension 설치.
* LiveCycle Rights Management ES2 이상 또는 AEM 6.0 Forms 이상을 위한 Document Security 추가 기능으로 향하도록 설치 관리자를 미리 구성합니다.
* 기본 정책 자동 애플리케이션 구성.

## 설치하기 전에 {#before-you-install}

Microsoft Office용 Document Security Extension을 설치하기 전에 다음을 확인하십시오.

* [릴리스 정보](document-security-extension-release-notes.md)를 읽었습니다.
* Microsoft Office가 활성화되었습니다. Microsoft Office 애플리케이션을 열 때 활성화 대화 상자가 나타나지 않습니다.
* Microsoft Windows 및 Microsoft Office용 최신 서비스 팩이 설치되었습니다.
* 지원되지 않는 언어에 대한 Microsoft Office용 Document Security를 설치하는 경우 최소 한 번 이상 Office 애플리케이션을 여십시오.

>[!NOTE]
>
>이름에 2바이트 문자가 포함된 폴더에 소프트웨어를 설치하지 마십시오. 그렇게 하면 AEM Document Security 메뉴가 Microsoft Office에 나타나지 않습니다.

>[!NOTE]
>
>64비트 운영 체제에 32비트 버전의 Document Security Extension을 설치하는 것은 지원되지만, 반대의 방법은 지원되지 않습니다. 32비트 운영 체제에는 64비트 버전의 Microsoft Office용 Document Security Extension을 설치할 수 없습니다.

### McAfee VirusScan 비활성화 {#disable-mcafee-virusscan}

McAfee VirusScan 콘솔에서 버퍼 오버플로 방지 옵션을 비활성화합니다. 이렇게 하면 Document Security Extension이 설치된 컴퓨터에서 Office 응용 프로그램을 원활하게 시작할 수 있습니다. 또한 McAfee VirusScan with On-Access Scan이 활성화됩니다. 이러한 조정은 시작 프로세스를 방해할 수 있는 충돌을 방지하는 데 도움이 됩니다.

### 서드파티 플러그인 제거 {#uninstall-third-party-plug-ins}

Microsoft Office용 AEM Document Security Extension은 Microsoft Office 애플리케이션용 서드 파티 플러그인을 지원하지 않습니다. 이 확장은 서드 파티 플러그인과 충돌하므로 Microsoft Office용 Security for Microsoft Office를 설치하기 전에 Microsoft Office용 비 Adobe 플러그인을 제거하십시오. Adobe는 서드 파티 플러그인이 설치된 Microsoft Office 애플리케이션용 Document Security를 지원하지 않습니다.

## 시스템 요구 사항 {#system-requirements}

### Document Security Extension 클라이언트 {#document-security-extension-client}

Document Security Extension을 설치할 다음 최소 구성을 확인하십시오.

* 영어, 프랑스어, 독일어, 일본어, 이탈리아어, 스페인어, 포르투갈어(브라질), 한국어, 중국어 간체 또는 중국어 번체로 된 32비트 또는 64비트 버전의 Microsoft Windows 7 또는 Windows 10.
  **참고:** *Microsoft Office용 문서 보안 확장 기능은 Microsoft Surface 디바이스에서도 작동합니다.*

* 32비트 또는 64비트 버전의 Office 2013, 2016, 2019 및 Microsoft Office 데스크탑 응용 프로그램은 영어, 프랑스어, 독일어, 일본어, 이탈리아어, 스페인어, 브라질 포르투갈어, 한국어, Simplified 중국어 또는 Traditional 중국어에 Office 365의 일부로 설치됩니다.

  **참고**: *Microsoft Office용 AEM Document Security Extension은 Microsoft Office 애플리케이션용 서드 파티 플러그인을 지원하지 않습니다. 이 확장은 서드 파티 플러그인과 충돌할 수 있으므로 Microsoft Office용 Document Security Extension을 설치하기 전에 Microsoft Office 애플리케이션용 Adobe 이외의 플러그인을 제거해야 합니다. Adobe는 서드 파티 플러그인이 설치된 Microsoft Office 애플리케이션용 Document Security Extension을 지원하지 않습니다.*

* 1.3GHz 프로세서 이상
* 2GB RAM
* 100MB의 하드 디스크 여유 공간

### 문서 보안 {#document-security}

Document Security Extension을 사용하려면 Adobe LiveCycle Rights Management ES2 이상 또는 AEM 6.0 Forms용 Document Security 추가 기능에 연결할 수 있는지 확인하십시오.

## Microsoft Office용 AEM Document Security Extension 설치 {#installing-document-security-extension-for-microsoft-office}

설치 관리자는 [다운로드 페이지](download-installer.md)에서 다운로드할 수 있습니다. 설치 관리자 실행 파일을 직접 맞춤화할 수는 없지만 상호 작용 방식으로 또는 자동 모드로 설치할 수 있습니다. 소프트웨어를 설치하려면 Windows에 관리자로 로그인하십시오.

32비트 및 64비트 버전의 Microsoft Office에 대해 별도의 설치 관리자를 사용할 수 있습니다. 32비트 버전의 Microsoft Office의 경우 DocumentSecurityExtensionforMicrosoftOffice.exe를 다운로드하십시오. 64비트 버전의 Microsoft Office에서는 다운로드 DocumentSecurityExtensionforMicrosoftOffice64.exe.

>[!NOTE]
>
>이 문서에서는 32비트 설치 관리자 파일(DocumentSecurityExtensionforMicrosoftOffice.exe)을 사용하여 다양한 명령과 옵션을 설명합니다. 64비트 버전의 Microsoft Office를 사용하는 경우 64비트 설치 관리자 파일(DocumentSecurityExtensionforMicrosoftOffice64.exe)을 사용하여 이 문서에 나열된 작업을 수행하십시오.

### 자동 모드로 설치 {#install-in-silent-mode}

WinZip과 같은 파일 추출기 유틸리티를 사용하여 설치 관리자 파일에서 `DocumentSecurityExtensionforMicrosoftOffice.exe`를 추출하십시오. 명령 프롬프트를 열고 설치 파일이 있는 폴더로 이동한 후 다음 텍스트를 입력하십시오.

`DocumentSecurityExtensionforMicrosoftOffice.exe -s -a -s -v" /qn"`

설치 관리자는 맞춤화에 사용할 수 있는 MSI 파일로도 제공됩니다.

### 자동 모드로 MSI 파일 설치 {#install-an-msi-file-in-silent-mode}

1. WinZip과 같은 파일 추출기 유틸리티를 사용하여 ZIP 파일에서 `DocumentSecurityExtensionforMicrosoftOffice.msi` 파일을 추출하십시오.

1. 명령 프롬프트를 열고 MSI 파일이 있는 폴더로 이동한 후 다음 텍스트를 입력하십시오.

   `msiexec /I DocumentSecurityExtensionforMicrosoftOffice.msi /qn`

## Document Security에 연결하도록 설치 관리자 미리 구성 {#preconfiguring-the-installer-to-connect-to-document-security}

LiveCycle 또는 AEM 서버를 가리키도록 Microsoft Office 설치 관리자용 Document Security Extension을 미리 구성할 수 있습니다. 이렇게 하면 Microsoft Office용 Document Security Extension을 설치하는 사용자가 연결을 구성하지 않고도 기능을 사용할 수 있습니다. 따라서 사용자는 구성할 필요 없이 보호된 문서를 열 수 있습니다. 그러나 특정 서버를 사용하도록 클라이언트를 구성할 때까지 새 문서를 보호할 수 없습니다.

다음 단계에서는 MSI 파일을 만들고 구성하는 방법을 설명합니다. 이 MSI 파일에는 레지스트리 값이 포함되어 있습니다. 이 값은 Microsoft Office 설치 관리자용 Document Security Extension을 기업에 설치된 LiveCycle 또는 AEM 서버에 미리 구성하는 데 필요합니다.

### 설치 관리자 맞춤화를 위한 사전 요구 사항 {#prerequisites-for-customizing-the-installer}

Orca 데이터베이스 편집기를 사용하여 설치 관리자를 맞춤화하십시오. 다음 단계에서는 Orca 데이터베이스 편집기를 사용하여 MSI 설치 파일의 사본을 수정하여 사용자 지정 MSI 파일을 만드는 방법을 설명합니다. Orca는 Windows Server 2008 및 .NET Framework 3.5용 Windows SDK의 일부로 사용할 수 있습니다.

<!--

For more information about how to edit Microsoft Windows&reg; Installer files using Orca, see [Microsoft Support](http://support.microsoft.com/kb/255905/EN-US/).

-->

>[!NOTE]
>
>사용자 지정 MSI 파일을 만들기 전에 모든 설치 관리자 파일을 전체 백업하는 것이 좋습니다.

#### Orca 설치 {#install-orca}

1. Windows Server 2008 및 .NET Framework 3.5용 Windows SDK 다운로드
1. \Microsoft SDK\bin 폴더에서 Orca.msi 파일을 더블 클릭합니다.

   설치 관리자 파일의 MSI 변형도 필요합니다. 최신 버전의 MSI 설치 관리자를 받으려면 Adobe 지원에 문의하십시오.

   >[!NOTE]
   >
   >설치 관리자를 실행하기 전에 항상 DocumentSecurityExtensionforMicrosoftOffice.msi 파일을 닫으십시오. Orca가 MSI 파일을 사용하는 경우 설치 관리자 실행할 수 없습니다.

### MSI 파일 생성 및 구성 {#create-and-configure-the-msi-file}

1. **[!UICONTROL 시작 > 프로그램 > Orca]**&#x200B;를 클릭합니다.

1. **[!UICONTROL 파일 > 열기]**&#x200B;를 클릭한 다음 `DocumentSecurityExtensionforMicrosoftOffice.msi` 파일을 찾습니다.

1. 테이블 목록(왼쪽)에서 속성을 선택합니다.

1. Rights Management 또는 Document Security의 엔터프라이즈 설치에 적용할 수 있는 다음 키 이름 값을 편집합니다.

<table>
 <tbody>
  <tr>
   <td><p><strong></strong><strong>키</strong><strong> 이름</strong></p> </td>
   <td><p><strong>설명</strong></p> </td>
   <td><p><strong></strong><strong>키</strong><strong> 값 기본값</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_NAME</code></p> </td>
   <td><p>이름을 표시합니다.</p> </td>
   <td><p>기본 서버</p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_URL</code></p> </td>
   <td><p>호스트 서버 URL</p> </td>
   <td><p>https://default.corp.com:1234</p> </td>
  </tr>
 </tbody>
</table>

1. 테이블 목록(왼쪽)에서 레지스트리를 선택합니다.

1. 다음 키 이름 값을 편집하십시오.

   | **키 이름** | **설명** | **키 값 기본값** |
   |---|---|---|
   | `IsDefault` | 기본 APS 서버. | 기본 서버 |

1. 수정된 파일을 원래 MSI 설치 관리자가 포함된 동일한 디렉터리에 저장합니다.

   >[!NOTE]
   >
   >일반적인 방법은 원래 MSI 파일과 동일한 파일 이름을 사용하는 것입니다(예: `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## 기본 정책의 자동 적용 구성 {#configuring-automatic-application-of-a-default-policy}

구성의 일부로 Microsoft Office용 Document Security Extension이 저장된 모든 문서를 보호하도록 기본 정책 자동 애플리케이션 프로그램을 구성할 수 있습니다.

다음 옵션 중 하나를 지정할 수 있습니다.

* 기본 정책으로 모든 문서를 보호합니다.
* 사용자가 서버에 연결할 수 없을 때 선택적으로 보호되지 않는 형식으로 파일을 저장할 수 있도록 허용합니다. 이러한 유연성 덕분에 사용자가 네트워크 연결이 끊어진 상태(예: 비행기 탑승 중)에서 문서를 만드는 경우를 고려할 수 있습니다.

자동 적용 정책 기능을 활성화하면 다음과 같은 경우 문서가 기본 정책으로 보호됩니다.

* 사용자가 새로 만든 문서를 편집하고 저장합니다.
* 사용자가 보호되지 않은 문서를 편집하고 저장함
* 사용자가 기본 문서로 열리는 응용 프로그램을 열고 편집한 다음 문서를 저장합니다

### MSI 파일에서 자동 적용 정책 기능 구성 {#configure-the-auto-apply-policy-feature-in-the-msi-file}

시작하기 전에 이 문서의 앞부분에서 설명한 대로 LiveCycle 또는 AEM Forms 서버를 가리키도록 설치 프로그램을 미리 구성하십시오.

1. **[!UICONTROL 시작 > 프로그램 > Orca]**&#x200B;를 클릭합니다.

1. **[!UICONTROL 파일 > 열기]**&#x200B;를 클릭한 다음 `DocumentSecurityExtensionforMicrosoftOffice.msi` 파일을 찾습니다.

1. 테이블 목록(왼쪽)에서 속성을 선택합니다.

1. Rights Management 또는 Document Security의 엔터프라이즈 설치에 적용할 수 있는 다음 키 이름 값을 편집합니다.

<table>
 <tbody>
  <tr>
   <td><p><strong>키 이름</strong></p> </td>
   <td><p><strong>설명</strong></p> </td>
   <td><p><strong></strong><strong>키</strong><strong> 값 기본값</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_IS_AUTO_ APPLY</code></p> </td>
   <td><p>자동 적용 정책 기능을 사용하거나 사용하지 않도록 설정합니다.</p> <p><code>1</code>: 사용</p> <p>0: 비활성화</p> </td>
   <td><p>0</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_POLICY_I D</code></p> </td>
   <td><p>정책은 새 문서를 저장할 때 사용할 GUID입니다. 이 값은 자동 적용 정책 기능에 적용됩니다.</p> </td>
   <td><p>RM 서버에 표시되는 16진수 정책 ID</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_U RL</code></p> </td>
   <td><p>서버 URL</p> </td>
   <td><p>default.corp.com</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_P ORT_NO</code></p> </td>
   <td><p>서버 포트 번호</p> </td>
   <td><p>1234</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE</code></p> </td>
   <td><p>클라이언트가 처음 저장할 때 문서를 보호하기 위해 서버에 접속할 수 없는 경우 Document Security 보호 없이 문서를 작성할 수 있는지 여부를 결정합니다.</p> <p>1: 보호되지 않은 저장 허용 </p> <p>0: 클라이언트가 문서를 저장하기 위해 서버에 접속할 수 없는 경우 새 문서 생성을 방지합니다.</p> </td>
   <td><p>0</p> </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>이 `AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE` 옵션은 고객에게 모든 문서를 보호하도록 강요하지 않고 보호하도록 상기시키려는 경우에 유용합니다. 사용자가 네트워크 연결이 끊어진 상태에서 문서를 작성한다는 사실을 알고 있는 경우에도 유용합니다. 문서 작성과 저장 기능은 계속 유지됩니다.

1. 수정된 파일을 원래 MSI 파일이 포함된 동일한 디렉터리에 저장합니다.

   >[!NOTE]
   >
   >일반적인 방법은 원래 MSI 파일과 동일한 파일 이름을 사용하는 것입니다(예: `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## 새 문서의 자동 보호 활성화 {#enabling-automatic-protection-of-new-documents}

관리자는 사용자 사용자가 저장한 문서를 자동으로 보호하는 기능을 사용하도록 설정할 수 있습니다. 관리자는 Microsoft Office용 Document Security Extension의 설치 프로그램에서 자동 적용 정책 기능을 구성합니다.

자동 적용 정책을 사용하는 경우 사용자가 저장하는 모든 문서는 기본 정책으로 보호됩니다. 이 조치는 다음 상황에 적용됩니다.

* 사용자가 새 문서를 작성하고 편집하고 저장하는 경우
* 사용자가 보호되지 않은 문서를 열고 편집한 후 저장하는 경우

자동 적용 정책 구성에 대한 자세한 내용은 [기본 정책의 자동 적용 구성](installing-configuring-aemdsext.md#p-configuring-automatic-application-of-a-default-policy-p)을 참조하십시오.

## 리본 없는 사용자 인터페이스 활성화 {#enable-ribbon-less-user-interface}

Windows 레지스트리에서 설정을 수정하여 리본 없는 사용자 인터페이스를 활성화/비활성화할 수 있습니다. 레지스트리를 업데이트하고 리본 없는 사용자 인터페이스를 활성화하려면 다음 단계를 수행하십시오.

1. 변경하기 전에 Windows 레지스트리를 백업하십시오. 자세한 지침은 [Windows 레지스트리 수정 방법](https://learn.microsoft.com/en-us/troubleshoot/windows-server/performance/windows-registry-advanced-users)을 참조하십시오.
1. 레지스트리 편집기에서 HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 또는 HKEY_LOCAL_MACHINE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0으로 이동합니다.
1. **HidePluginUI**&#x200B;라는 새 Dword(32비트) 값을 만듭니다.

1. 리본 없는 사용자 인터페이스를 사용하려면 **HidePluginUI** 속성 값을 1로 설정하십시오.

1. 레지스트리 편집기를 닫습니다.

## Microsoft Excel에서 인쇄하기 위해 워터마크 활성화 {#enable-watermark-for-printing-in-microsoft-excel}

동적 워터마크가 기존 머리글 및 바닥글과 함께 존재하도록 Windows 레지스트리 설정을 변경할 수 있습니다. 레지스트리 설정은 인쇄 중에만 워터마크를 사용할 수 있도록 합니다. 다음 단계를 수행하여 레지스트리를 업데이트하고 인쇄하는 동안 워터마크를 활성화하십시오.

1. 변경하기 전에 Windows 레지스트리를 백업 하십시오. 자세한 지침은 [Windows 레지스트리 수정 방법](https://learn.microsoft.com/en-us/troubleshoot/windows-server/performance/windows-registry-advanced-users)을 참조하십시오.
1. 레지스트리 편집기에서 HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 또는 HKEY_LOCAL_MACHINE\WOW6432NODE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0으로 이동합니다.
1. 새 레지스트리 키 **WatermarkMode**&#x200B;를 만듭니다.
1. WatermarkMode 레지스트리 키에서 DWORD **WatermarkMode**&#x200B;을(를) 만들고 DWORD **WatermarkMode**&#x200B;의 값을 **1**(으)로 설정합니다.

1. 레지스트리 편집기를 닫습니다.

>[!NOTE]
>
>Windows 탐색기에서 파일 메뉴 또는 컨텍스트 메뉴를 사용하여 Microsoft Excel 문서를 만들 수 있습니다. 명시된 방법으로 작성된 문서의 경우 인쇄 날짜를 검색하거나 변경할 수 없습니다. Microsoft Excel의 제한 사항입니다. AEM Document Security 워터마크는 문서의 인쇄 날짜에 따라 달라집니다. 따라서 이러한 문서의 경우 워터마크가 이전 날짜로 되돌아갑니다. 또한 머리글과 바닥글도 유지되지 않습니다.

## 문서에 사용자 지정 표지 추가 {#coverpage}

사용자는 Microsoft Office용 AEM Document Security 플러그인이 설치되지 않은 컴퓨터에서 보호된 문서를 열려고 할 수 있습니다. 이러한 컴퓨터는 문서를 열 수 없습니다. 이러한 컴퓨터에서 Microsoft Office용 AEM Document Security 플러그인 및 기타 정보를 다운로드하기 위한 지침이 포함된 표지를 표시할 수 있습니다.

### 표지를 구성하기 전에 {#before-you-configure-a-cover-page}

* CommonResources.dll 파일을 백업하십시오. 기본 경로는 다음과 같습니다.

   * **(32비트 컴퓨터의 32비트 Office의 경우)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **(64비트 컴퓨터의 32비트 Office의 경우)** C:\Program Files (x86)\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **64비트 컴퓨터의 64비트 Office의 경우)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

* Microsoft Visual Studio 2008 이상이 설치되어 있는지 확인하십시오. 다른 유틸리티를 사용하여 DLL 파일을 편집할 수도 있습니다.
* templates.zip 아카이브를 추출하십시오. 아카이브에는 표지용 .xlsx, .docx 및 .pptx 템플릿이 포함되어 있습니다. .xlsx, .docx 및 .pptx 파일 형식에 대해 제공된 템플릿만 사용하십시오. 다른 파일 유형을 위한 자체 템플릿을 만들 수 있습니다. 사용자 지정 메시지 및 지침을 포함하도록 템플릿을 사용자 지정합니다. 다음에서 template.zip을 찾을 수 있습니다.

[파일 가져오기](assets/templates.zip)

### CommonResources.dll 파일의 구조 {#structure-of-the-commonresources-dll-file}

CommonResources.dll 파일에는 리소스 템플릿에 대한 정보가 포함되어 있습니다. 여기에는 두 개의 이름 식별자(TEMPLATE_FILE 및 RT_MANIFEST)가 포함되어 있습니다. 사용자 지정 표지를 활성화하기 위해 TEMPLATE_FILE 이름 식별자가 수정됩니다. TEMPLATE_FILE 이름 식별자에는 6개의 리소스가 있습니다.

<table>
 <tbody>
  <tr>
   <td><p><strong>리소스</strong></p> </td>
   <td><p><strong>표현 </strong></p> </td>
  </tr>
  <tr>
   <td><p>101 </p> </td>
   <td><p>.xls</p> </td>
  </tr>
  <tr>
   <td><p>102</p> </td>
   <td><p>.doc</p> </td>
  </tr>
  <tr>
   <td><p>103 </p> </td>
   <td><p>.ppt</p> </td>
  </tr>
  <tr>
   <td><p>104 </p> </td>
   <td><p>.xlsx</p> </td>
  </tr>
  <tr>
   <td><p>105</p> </td>
   <td><p>.docx</p> </td>
  </tr>
  <tr>
   <td><p>106</p> </td>
   <td><p>.pptx</p> </td>
  </tr>
 </tbody>
</table>

#### 템플릿을 표지로 구성 {#configure-the-template-as-a-cover-page}

1. Microsoft Visual Studio를 엽니다. 편집할 CommonResources.dll 파일을 찾아서 엽니다.

   >[!NOTE]
   >
   >파일이 솔루션 탐색기 창에 나타나지 않으면 연결 프로그램 옵션을 사용하여 파일을 다시 엽니다. 리소스 편집기를 편집기로 선택합니다.

1. 솔루션 탐색기 창에서 TEMPLATE_FILE 디렉터리를 확장하고 리소스 101을 삭제합니다.

1. 리소스를 추가합니다.

   1. 솔루션 탐색기에서 프로젝트를 선택한 상태에서 프로젝트 메뉴에서 속성을 클릭합니다.
   1. 리소스 탭을 선택합니다.
   1. 리소스 디자이너 도구 모음에서 리소스 추가를 가리키고 화살표를 클릭합니다. 리소스 유형으로 TEMPLATE_FILE을 선택하고 가져오기를 클릭합니다.
   1. **`Add existing file to resources`** 대화 상자에서 Resource.xlsx 파일을 찾은 다음 열기를 클릭합니다. 파일이 TEMPLATE_FILE 디렉터리에 추가됩니다.

   >[!NOTE]
   >
   >언어 설정이 올바른지 확인합니다. 중립 언어로 리소스를 삭제합니다.

1. 모든 리소스 유형에 대해 2단계와 3단계를 반복합니다.

   >[!NOTE]
   >
   >리소스 유형을 삭제하고 임의의 순서로 추가하지 마십시오. 101 이후에 102를 구성하는 식입니다.

### Microsoft Office용 AEM Document Security 확장 설치 관리자를 사용하여 사용자 지정 CommonResources.dll 파일 패키징 {#package-custom-commonresources-dll-file-with-the-installer-of-aem-document-security-extension-for-microsoft-office}

CommonResources.dll 파일을 사용자 지정하여 사용자 지정 표지를 추가할 수 있습니다. 파일을 사용자 지정한 후 모든 워크스테이션에서 원본 파일을 사용자 지정 파일로 수동으로 바꾸거나 자동화된 방법을 선택하여 파일을 바꿀 수 있습니다.

대규모 환경에서는 기본 `CommonResources.dll file`을(를) 사용자 지정 `CommonResources.dll` 파일로 수동으로 바꾸는 것은 어렵고 지루한 일입니다. 자동 압축 풀기 및 패키징 도구(예: WinZip Self-Extractor)를 사용하여 Microsoft Office용 AEM Document Security Extension 설치 관리자로 사용자 지정 CommonResources.dll 파일을 패키징할 수 있습니다. 나중에 사용자 지정 설치 관리자를 모든 워크스테이션에 배포할 수 있습니다. 이 방법은 기본 `CommonResources.dll` 파일을 사용자 지정 파일로 바꾸는 데 필요한 시간을 줄여 줍니다. 또한 모든 워크스테이션에 필요한 CommonResources.dll 파일이 있는지 확인합니다. 자동 압축 풀기 및 패키징 도구는 파일을 자동으로 대체할 수 있는 다양한 방법 중 하나일 뿐입니다. 자신의 환경에 적합한 방법을 선택할 수 있습니다.

다음 단계를 수행하여 Microsoft Office용 AEM Document Security 확장 설치 관리자를 사용하여 사용자 지정 `CommonResources.dll`파일을 패키징할 수 있습니다.

1. 자동 압축 풀기 및 패키지 도구를 설치합니다. 예를 들어, WinZip Self-Extractor가 있습니다.
1. 새 폴더를 만듭니다. 예: YOUR_FOLDER_NAME
1. AEM Document Security Extension의 원래 설치 관리자 및 사용자 지정 CommonResources.dll 파일을 새로 만든 폴더에 저장합니다.
1. 폴더에 배치 파일을 만듭니다. 예: YOUR_FOLDER_NAME\Installer.bat
1. 편집할 배치 파일을 열고 배치 파일에 다음 코드를 추가합니다.

   ```shell
    @echo off
   
    setlocal EnableDelayedExpansion
   
    msiexec /i YOUR_FOLDER_NAME\MSI_NAME.exe
   
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\HARDWARE\DESCRIPTION\System\CentralProcessor\0" /v "Identifier"') DO set "IDENTIFIER=%%B"
   
    set IDENTIFIER= %IDENTIFIER: =%
   
    if not %IDENTIFIER:x86=%==%IDENTIFIER% (
   
    REM Fetching install path for 32 bit machine.
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
    ) else (
   
        REM Fetching install path for 64 bit machine.
   
            FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Wow6432Node\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
        )
   
    COPY "YOUR_FOLDER_NAME\CommonResources.dll" "%INSTALLPATH%"
   
    endlocal
   ```

   LiveCycle Rights Management ES4 및 11.0.0 버전을 제외하고 JEE의 다른 버전의 LiveCycle 또는 AEM Forms을 사용하는 경우 다음과 같이 레지스트리 키의 경로를 바꿉니다.

   * (LiveCycle® Rights Management ES2 및 버전 9.0): *HKLM\SOFTWARE\Adobe/LiveCycle* *Rights Management ES2\9.0 *
   * (LiveCycle® Rights Management ES3 및 버전 10.0)
   * (LiveCycle® Rights Management ES4 및 버전 11.0) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0
   * (JEE의 AEM 6.0 Forms 이상 버전) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0

1. 위 코드에서 YOUR_FOLDER_NAME의 모든 인스턴스를 2단계에서 만든 폴더의 이름으로 바꿉니다.
1. **(.exe 확장자가 AEM Microsoft Office용 Document Security Extension 설치 프로그램만 해당)** 다음 코드 줄을 바꾸기

   `msiexec /i YOUR_FOLDER_NAME\MSI_NAME.msi`
with

   `START /w YOUR_FOLDER_NAME\APPLICATION_NAME.exe`

1. 배치 파일을 저장하고 닫습니다.
1. 자동 압축 풀기 및 패키지 작성 도구를 사용하여 다음을 포함하는 폴더를 패키징합니다.

   * 사용자 지정 CommonResources.dll 파일
   * Microsoft Office용 AEM Document Security 확장의 원본 설치 프로그램
   * 그리고, 배치 파일

   >[!NOTE]
   >
   >자동 압축 풀기 패키지가 관리자 권한으로 실행되도록 설정되어 있고 자동으로
   >추출 완료 시 배치 파일을 실행합니다.

이제 AEM Document Security Extension for Microsoft Office의 자동 압축 풀기 설치 관리자가 사용자 지정 CommonResources.dll 파일을 패키지화하여 배포할 준비가 되었습니다.
