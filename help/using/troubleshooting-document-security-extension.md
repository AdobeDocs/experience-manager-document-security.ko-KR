---
title: Microsoft Office용 AEM Document Security Extension 문제 해결
description: Microsoft Office용 AEM Document Security Extension을 설치, 구성 또는 사용하는 데 문제가 있는 경우 이 문서에 기재되어 있는 지침을 따르십시오.
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
exl-id: 98f24032-0774-47f8-bcc5-1ee37b417833
TQID: https://experienceleague.adobe.com/3YVMcSeYDXCWkVeG8HmlJOgja9OwLqs1gpPWP8rhhs0
product_v2: id: e8f6de9b-cf88-4405-8d10-15efa08c230eid: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: fd5d26fd-7180-407d-bbd8-5f8a17f9c0b8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: b2df949228acdc23ca7f2c55b72e62c1dba130b8
workflow-type: tm+mt
source-wordcount: 316
ht-degree: 100%

---

# Microsoft Office용 AEM Document Security Extension 문제 해결{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## 설치 및 구성 문제 해결 {#troubleshootinginstallationandconfiguration}

Microsoft Office용 AEM Document Security Extension을 설치하고 구성하는 데 문제가 있는 경우 - 설치 전- [설치](installing-configuring-aemdsext.md) 문서의 섹션에 기재되어 있는 지침을 주의 깊게 따랐는지 확인하십시오.

문서에 따라 모든 것을 설치하고 구성한 경우 발생하는 것과 유사한 문제들을 다음 섹션에서 검토하십시오.

### Document Security Extension이 Microsoft Office 애플리케이션에 대해 로드되지 않음 {#document-security-extension-fails-to-load-for-microsoft-office-applications}

Windows 레지스트리의 LoadBehavior 속성은 문서 보안 플러그인의 런타임 동작을 지정합니다. LoadBehavior 속성이 3으로 설정되면 모든 플러그인이 자동으로 로드됩니다. Microsoft Office용 Document Security Extension 을 설치하기 전에 LoadBehavior 속성 값이 3으로 설정되어 있는지 확인하십시오.

1. 변경하기 전에 Windows 레지스트리를 백업하십시오. 자세한 지침은 [Windows 레지스트리 수정 방법](https://learn.microsoft.com/en-us/troubleshoot/windows-server/performance/windows-registry-advanced-users)을 참조하십시오.
1. 레지스트리 편집기에서 HKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin 또는 HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM으로 이동합니다.
1. **LoadBehavior** 속성의 값을 3으로 설정합니다.

1. 레지스트리 편집기를 닫습니다.

LoadBehavior에 대한 자세한 내용은 [VSTO 추가 기능의 레지스트리 항목](https://learn.microsoft.com/en-us/visualstudio/vsto/registry-entries-for-vsto-add-ins?view=vs-2022&redirectedfrom=MSDN#LoadBehavior) 문서를 참조하십시오.

## 관리 작업 문제 해결 {#admintasks}

이 섹션에서는 설치된 AEM Document Security Extension의 발생 가능한 문제에 대해 설명합니다.

### Document Security Extension 설치 시 Microsoft Office 애플리케이션이 원활하게 시작되지 않음 {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

Document Security가 설치되어 있고 실시간 검색이 활성화된 McAfee VirusScan이 있는 컴퓨터에서 Office 애플리케이션이 원활하게 시작되도록 하려면 McAfee VirusScan 콘솔에서 버퍼 오버플로 방지를 비활성화하십시오.
