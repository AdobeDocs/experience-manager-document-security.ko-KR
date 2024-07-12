---
title: Microsoft&reg; Office용 AEM Document Security Extension 소개
description: Microsoft&reg; Office용 Document Security Extension을 사용하면 미리 정의된 기밀 유지 설정을 Microsoft&reg; Office 파일에 적용할 수 있습니다.
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
exl-id: 3e07c031-3f88-4bde-bdb3-b136ef5f9527
source-git-commit: 28137f26afc024d411857d44887bf69fe1ee2b81
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 100%

---

# Microsoft® Office용 AEM Document Security Extension 소개{#introduction-to-aem-document-security-extension-for-microsoft-office}

Microsoft® Office 용 Adobe® Experience Manager Document Security Extension을 사용하면 귀하가 승인한 사람만 지적 재산이 포함된 Word, Excel 및 PowerPoint 파일을 사용할 수 있습니다. Microsoft® Office용 문서 보안 확장을 사용하면 미리 정의된 기밀 설정을 파일에 적용할 수 있습니다.

Microsoft® Office용 Document Security Extension은 LiveCycle Rights Management 및 Adobe Experience Manager Forms용 Document Security 추가 기능을 확장하여 Word, Excel 및 PowerPoint 파일을 보호하고 이 소프트웨어를 설치한 인가된 사용자가 정책에 확립된 기밀 유지 설정에 따라 정책으로 보호된 파일을 사용할 수 있도록 합니다.

## Document Security가 지적 재산을 보호하는 방법 {#how-document-security-protects-intellectual-property}

Document Security는 귀하가 승인한 사람만 귀하의 지적 재산이 포함된 파일을 사용할 수 있도록 합니다. Document Security를 사용하면 기밀 유지 정책을 사용하여 파일을 보호할 수 있습니다. *정책*&#x200B;은 기밀성 설정 및 인가된 사용자 목록을 포함하는 정보의 모음입니다. 귀하가 정책에 지정하는 설정은 정책이 적용되는 파일을 수신자가 어떻게 사용할 수 있는지를 결정합니다. 예를 들어 수신자가 텍스트를 인쇄 또는 복사하거나 변경 사항을 저장할 수 있는지 여부를 지정할 수 있습니다.

Document Security 관리자와 사용자는 정책을 수립합니다. 관리자는 모든 인가된 사용자가 사용할 수 있는 조직 정책을 수립합니다. 관리자 또는 정책 세트 코디네이터는 사용자 하위 집합이 사용할 수 있는 *정책 세트*&#x200B;라는 정책 그룹을 생성할 수도 있습니다. 사용자는 자신만 사용할 수 있는 자체 정책을 만들 수 있습니다. 관리자, 정책 세트 코디네이터, 사용자는 Document Security 웹 페이지를 사용하여 정책을 수립합니다.

정책은 Document Security에 저장되지만 Word, Excel 또는 PowerPoint를 통해 파일에 적용합니다. 파일에 정책을 적용하면 파일에 포함된 정보는 정책에 지정된 기밀 유지 설정에 의해 보호됩니다. 정책으로 보호된 파일을 배포하면 정책에 의해 승인된 수신자만 파일의 내용에 액세스할 수 있습니다.

정책을 사용하여 파일을 보호하면 배포 후에도 해당 파일을 지속적으로 제어할 수 있습니다. 이벤트를 감사하여 수신자가 언제 어떻게 파일을 사용하는지 추적하고, 정책을 변경하고, 사용자가 파일에 계속 액세스하지 못하도록 하고, 파일에 첨부된 정책을 변경할 수 있습니다.

## 정책 작동 방식 {#how-policies-work}

정책에는 인가된 사용자 및 지적 재산에 적용할 기밀 유지 설정에 대한 정보가 포함되어 있습니다. 링크된 LDAP 또는 Active Directory 목록에 포함되어 Document Security에서 인식되는 모든 사용자는 사용자가 될 수 있습니다. Document Security에 등록하도록 초대되었거나 관리자가 계정을 만든 사람도 사용자가 될 수 있습니다.

정책의 기밀 유지 설정은 정책으로 보호되는 파일을 수신자가 어떻게 사용할 수 있는지를 결정합니다. 예를 들어 정책은 수신자가 파일을 인쇄할 수 있는지, 콘텐츠를 다른 파일에 복사할 수 있는지 또는 보호된 파일에 변경 사항을 저장할 수 있는지 여부를 지정합니다. 정책은 다양한 사용자에 대해 서로 다른 기밀 유지 설정을 지정할 수도 있습니다.

파일에 정책을 적용하면 파일에 포함된 정보는 정책에 지정된 기밀 유지 설정에 의해 보호됩니다. 파일을 배포할 때 Document Security는 파일을 열려고 하는 수신자를 인증하고 정책에 지정된 권한에 따라 액세스 권한을 부여합니다.

정책이 파일에 적용된 후 언제든지 정책의 기밀 유지 설정을 변경할 수 있습니다. 이때 인가된 사용자를 추가 또는 제거하거나 사용자가 파일을 수신한 후 해당 사용자의 권한을 변경할 수 있습니다. 파일에 적용된 정책은 변경될 수 있으며, 파일 사본이 있는 사용자가 더 이상 해당 파일을 열 수 없도록 파일에 대한 액세스 권한이 취소될 수 있습니다.

정책이 오프라인 액세스를 허용하는 경우 수신자는 정책에 지정된 기간 동안 정책으로 보호된 파일을 오프라인으로(활성 인터넷 또는 네트워크 연결 없이) 사용할 수도 있습니다.

## 정책으로 보호된 파일의 작동 방식 {#how-policy-protected-files-work}

사용자가 정책으로 보호된 Word, Excel 및 PowerPoint 파일을 열고 사용하려면 정책에 사용자를 수신자로 포함하거나 익명 액세스를 허용해야 합니다. 또한 사용자에게 Microsoft® Office용 문서 보안 확장이 설치되어 있어야 합니다. Microsoft® Office용 Document Security Extension이 없는 사람에게 정책으로 보호된 파일을 제공하려면 소프트웨어 사본을 제공하거나 웹 사이트에서 다운로드하는 방법을 알려주십시오. 설치 관리자가 없는 경우 [다운로드 페이지](https://experienceleague.adobe.com/docs/experience-manager-document-security/using/download-installer.html?lang=en)에서 다운로드할 수 있습니다.

사용자가 정책으로 보호된 파일을 열려고 하면 Microsoft® Office용 Document Security Extension은 사용자를 인증하기 위해 Document Security에 연결합니다. Document Security가 파일 사용을 감사하도록 구성된 경우 파일 사용이 감사되고 있음을 나타내는 알림이 사용자에게 표시됩니다. 다음 조건하에서, Document Security는 사용자에게 부여할 파일 권한을 결정하고 사용자는 정책 설정에 따라 파일을 사용할 수 있습니다.

* 정책에 지정된 유효 기간 동안.
* 관리자 또는 정책을 적용한 사람이 파일에 대한 액세스를 취소하거나 정책을 변경할 때까지.

  정책을 적용한 사람이 정책을 변경하거나 파일에 대한 액세스 권한을 취소하면 사용자가 이미 파일을 가지고 있더라도 파일에 대한 사용자의 권한이 변경되거나 제거됩니다. 파일 자체가 취소된 경우 업데이트된 사본을 얻을 수 있도록 사용자에게 URL이 제공될 수 있습니다.

  정책이 오프라인 액세스를 허용하는 경우 정책에 지정된 오프라인 임대 기간 동안 정책으로 보호된 파일을 오프라인으로(인터넷 또는 네트워크 연결 없이) 열 수 있습니다. 오프라인 임대 기간이 종료되면 사용자는 온라인으로 전환하고 Document Security와 동기화하여 새 임대 기간을 시작해야 합니다.

  정책에서 파일 저장을 허용하고 사용자가 정책으로 보호된 파일의 사본을 저장하면 저장된 파일에 대해 정책이 자동으로 적용되고 시행됩니다. 새 파일 열기 시도와 같은 이벤트도 원본 파일과 동일하게 감사되고 기록됩니다.

## Document Security를 사용하여 파일 보호 {#using-document-security-to-protect-your-files}

정책을 사용하여 다양한 상황에서 파일을 보호할 수 있습니다.

예를 들어 제조업체가 새 제품에 대한 부품을 제공하는 공급업체의 입찰을 수락합니다. 제조업체는 입찰 제출을 완료하기 위한 독점적 정보를 입찰자에게 제공해야 합니다. 제조업체는 Document Security를 사용하여 입찰자가 파일을 열고 정보를 볼 수 있도록 하는 정책으로 파일을 보호합니다. 그러나 입찰자는 파일을 변경, 인쇄 또는 복사할 수 없으며 권한이 없는 사람은 파일을 열 수 없습니다.

입찰 중 하나를 수락한 후에 제조업체는 정책을 업데이트하여 로컬에서 인쇄하고 복사하고 변경 사항을 저장할 수 있는 권한을 낙찰자에게 부여하고, 실패한 입찰자는 파일을 열 수 있는 권한이 더 이상 없도록 제거합니다.

낙찰자와 함께 작업하는 동안 제조업체의 엔지니어는 파일의 일부 디자인 사양을 변경합니다. 새 사양을 게시하기 위해 제조업체는 일부 파일에 대한 액세스를 취소하고 새 버전을 게시합니다. 낙찰자의 엔지니어가 파일을 열려고 하면 파일에 대한 액세스가 취소되었다는 메시지가 표시됩니다. 메시지에는 파일의 새 버전을 다운로드할 수 있는 URL이 포함되어 있습니다.

## 추가 정보 {#additional-information}

이 표의 리소스는 AEM Document Security에 대해 자세히 알아 보는 데 도움이 될 수 있습니다.

<table >
 <tbody>
  <tr>
   <th><p>다음에 대한</p> </th>
   <th><p>자세한 내용은</p> </th>
  </tr>
  <tr>
   <td><p>AEM Forms 관리자 도움말</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/docs/experience-manager-65/forms/administrator-help/get-started/configure-general-aem-forms-settings.html?lang=en">관리자 도움말</a>을 참조하거나 Document Security 관리 페이지에서 페이지의 오른쪽 상단에 있는 도움말 링크를 클릭하십시오.</p> </td>
  </tr>
  <tr>
   <td><p>이 제품 버전에 대한 패치 업데이트, 기술 참고 사항 및 추가 정보</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/?support-solution=General&amp;support-tab=home#support">Experience Cloud 기술 지원</a></p> </td>
  </tr>
 </tbody>
</table>
