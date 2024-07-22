---
title: Microsoft Office용 AEM Document Security - 릴리스 정보
description: Microsoft Office용 AEM Document Security 6.2 Extension을 설치하기 전에 릴리스 정보를 읽으십시오.
uuid: f6ab73d4-ac4e-4fff-9bb8-917b75401653
content-type: reference
topic-tags: installing
discoiquuid: c9342c28-8289-4831-a613-4bc03431f557
exl-id: 582f10bb-60d2-46ed-b81d-5818a040edc6
source-git-commit: 3b6a686966fb8d006bed8cc4a4bf5eebe0dfb030
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 73%

---

# Microsoft Office용 AEM Document Security - 릴리스 정보{#aem-document-security-for-microsoft-office-release-notes}

## Microsoft Office용 AEM Document Security의 새로운 기능 {#whats-new-in-aem-document-security-for-microsoft-office}

* **Office 2019 지원**: Microsoft Office용 Document Security Extension에 Microsoft Office 2019에 대한 지원이 추가되었습니다. 또한 Office 365의 일부로 설치된 Microsoft Office 2019 데스크탑 애플리케이션에서도 작동합니다.

>[!NOTE]
>
>이 문서에서는 다음과 같은 용어를 서로 교환하여 사용합니다.
>
>* Microsoft Office용 Adobe Experience Manager Document Security
>* Microsoft Office용 Adobe Experience Manager 문서 보안 확장
>* Microsoft Office용 문서 보안 확장

## Microsoft Office용 AEM Document Security Extension 설치 및 구성 {#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

이 Microsoft Office용 Document Security Extension 버전은 Adobe LiveCycle Rights Management ES2 이상 및 AEM Forms용 Document Security 추가 기능과 호환됩니다.

Microsoft Office용 AEM Document Security Extension을 설치하기 전에 이 문서의 정보를 검토하십시오. 자세한 설치 지침은 [Microsoft Office용 AEM Document Security Extension 설치 및 구성](installing-configuring-aemdsext.md) 문서를 참조하십시오.

## 해결된 문제 {#fixed-issues}

* 문자열이 세로로 표시되고 잘못된 줄 바꿈이 내용에 추가됩니다. (CQ-4201054)

## 알려진 문제 {#known-issues}

### 서드파티 플러그인이 지원되지 않음 {#third-party-plug-ins-not-supported}

Microsoft Office용 AEM Document Security Extension은 서드파티 플러그인에서 작동하지 않습니다. Microsoft Office용 Document Security Extension을 설치하기 전에 Microsoft Office용 서드 파티 플러그인을 제거하십시오.

### Microsoft Word, Excel 및 PowerPoint에서 비활성화된 메뉴 옵션 {#disabled-menu-options-in-microsoft-word-excel-and-powerpoint}

Microsoft Office용 AEM Document Security Extension은 기본 제공 보호 기능을 사용하여 문서, 워크시트 및 프레젠테이션을 보호합니다. 몇 가지 Excel, Word 및 PowerPoint 메뉴 옵션을 비활성화합니다.

### Microsoft Office 2013, 2016 및 2019에 대한 제한 사항 {#restrictions-for-microsoft-office}

Microsoft Office에서는 보호된 세션 중에 다음 옵션을 사용할 수 없습니다.

* Microsoft Office 2016 또는 Microsoft Office 2019

   * 파일 > 다른 이름으로 저장
   * 파일 > 기록
   * 파일 > 공유
   * 파일 > 내보내기
   * 파일 > 게시
   * 파일 > 계정
   * 파일 > 정보 > 문서/통합 문서/프레젠테이션 보호 > 암호 설정
   * 파일 > 정보 > 문서 보호 > 디지털 서명 추가
   * 파일 > 정보 > 문서 보호 > 최종본으로 표시
   * 오른쪽 상단의 공유 옵션

* Microsoft Office 2013

   * 파일 > 다른 이름으로 저장
   * 파일 > 공유
   * 파일 > 내보내기
   * 파일 > 계정
   * 파일 > 정보 > 문서/통합 문서/프레젠테이션 보호 > 암호 설정
   * 파일 > 정보 > 문서 보호 > 디지털 서명 추가
   * 파일 > 정보 > 문서 보호 > 최종본으로 표시

### SharePoint Server에서 보호된 문서 열기 {#opening-a-protected-document-from-sharepoint-server}

SharePoint Server로부터 Microsoft Office용 Document Security Extension에서 보호된 문서를 열려면 먼저 연관된 Microsoft Office 프로그램(Word, Excel 또는 PowerPoint)을 여십시오. 그렇지 않으면 문서가 열리지 않을 수 있습니다. 해당 플러그인을 설치했음을 나타내는 오류 메시지가 표시됩니다. 따라서 SharePoint Server의 Microsoft Office용 Document Security Extension에서 보호된 문서를 열기 전에 관련 Microsoft Office 프로그램을 여는 것이 좋습니다.

(선택 사항) SharePoint Server로부터 Microsoft Office용 Document Security Extension에서 보호된 문서를 열기 전에 캐시 폴더를 지우는 것이 좋습니다.

SharePoint Server로부터 보호된 문서를 열면 적용된 정책에 관계없이 문서에 대한 모든 권한이 비활성화됩니다.

### 프린터가 설치되지 않은 상태에서 Microsoft Excel 2013, Microsoft Excel 2016 및 Microsoft Excel 2019 파일에 동적 워터마크가 포함된 정책 적용 {#apply-a-policy-with-a-dynamic-watermark-to-microsoft-excel-microsoft-excel-and-microsoft-excel-file-with-no-printer-installed}

프린터가 설치되지 않은 컴퓨터에서 Excel 2013, 2016 또는 2019 파일에 동적 워터마크가 포함된 정책을 적용하면 &quot;동적 워터마크를 적용하는 동안 내부 오류가 발생했습니다&quot;라는 오류가 발생합니다. 이 오류는 보호된 파일을 다시 열 때도 나타납니다. 워터마크가 적용되지 않으며 보기 > 페이지 레이아웃에서 워터마크를 볼 수 없습니다.

### 지원되는 Office 애플리케이션에 대한 Windows 데이터 실행 방지 비활성화 {#disable-windows-data-execution-prevention-for-supported-office-applications}

Microsoft Office 애플리케이션용 Document Security Extension을 사용할 때는 Windows DEP(데이터 실행 방지) 설정을 비활성화하는 것이 좋습니다.

### Document Security Extension을 사용하여 공유 Microsoft Office 파일을 보호할 수 없음 {#shared-microsoft-office-files-cannot-be-protected-using-document-security-extension}

Document Security Extension을 사용하여 공유 Microsoft Office 파일을 보호하면 오류가 발생하고 공유 파일이 보호되지 않습니다.

### Microsoft Office용 Document Security Extension 및 McAfee VirusScan이 포함된 컴퓨터에서 Office 애플리케이션시작 {#starting-office-applications-on-a-machine-containing-document-security-extension-for-microsoft-office-and-mcafee-virusscan}

Document Security와 McAfee VirusScan(실시간 검색 사용)이 있는 컴퓨터에서 Office 응용 프로그램을 원활하게 시작하려면 McAfee VirusScan 콘솔에서 버퍼 오버플로 방지 옵션을 비활성화하십시오.

### 지원되지 않는 Microsoft Office 언어를 사용하는 시스템에 Microsoft Office용 Document Security Extension 설치 {#installing-document-security-extension-for-microsoft-office-on-a-machine-with-an-unsupported-microsoft-office-language}

지원되지 않는 언어를 사용하는 Microsoft Office 애플리케이션이 있는 컴퓨터에 Microsoft Office용 Document Security Extension을 설치하기 전에 Office 애플리케이션을 한 번 이상 여십시오.

### 사용자에게 오프라인 권한이 없는 경우에도 오프라인 동기화 버튼이 활성화됨 {#synchronize-offline-button-is-enabled-even-when-a-user-does-not-have-offline-permissions}

사용자에게 문서에 대한 오프라인 권한이 없는 경우에도 오프라인 동기화 버튼이 제공될 수 있습니다. 그러나 버튼을 선택해도 아무 작업도 수행되지 않습니다.

### Microsoft Office 체험판이 지원되지 않음 {#no-support-for-trial-versions-of-microsoft-office}

Microsoft Office용 Document Security Extension은 Microsoft Office의 추적 버전을 지원하지 않습니다. 확장을 설치하기 전에 Microsoft Office의 라이선스가 있는 사본을 설치했고 활성화되어 있는지 확인하십시오.

### 보호된 Microsoft Office 파일을 열 수 없음 {#unable-to-open-a-protected-microsoft-office-files}

Microsoft Office의 보호된 보기가 활성화된 경우 Right Management Extension은 원격 위치에서 보호된 Microsoft Excel 파일(XLS, XLSX) 및 보호된 Microsoft PowerPoint(PPT) 파일을 열 수 없습니다.

### 이미지 또는 배경색이 포함된 Microsoft Excel 문서의 셀이 워터마크 위에 나타남 {#cells-of-microsoft-excel-document-containing-an-image-or-background-color-appear-on-top-of-watermark}

Excel 문서의 셀에 이미지 또는 배경색이 있는 경우 동적 워터마크가 적용되면 이미지 또는 색상이 워터마크를 덮습니다. 이 접근법은 워터마크가 셀에서 이미지 또는 배경색에 의해 가려진다는 것을 의미한다.

### 여러 인증서의 사용성 문제 {#usability-issue-with-multiple-certificates}

클라이언트 시스템에 인증서가 여러 개 있고 사용자가 인증서 선택 대화 상자를 취소하면 대화 상자가 다시 나타납니다. 대화 상자를 두 번 취소해야 합니다.

### Microsoft PowerPoint에서 보호된 문서 편집을 허용 {#microsoft-powerpoint-allows-editing-protected-documents}

보호된 문서를 편집하려고 하면 Microsoft PowerPoint에서 “이 문서를 수정할 수 있는 권한이 없습니다. 변경 사항을 저장할 수 없습니다.&quot; 메시지를 닫은 후에도 사용자는 계속해서 텍스트를 추가하거나 문서를 편집할 수 있습니다. 그러나 보호된 문서의 변경 사항은 저장되지 않습니다.

위에서 언급한 동작은 PowerPoint 2013, PowerPoint 2016 및 PowerPoint 2019에서 예상되는 것과 같습니다.
