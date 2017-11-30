---
title: '&lt;serviceCertificate&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 177639b973bf8c597bc8b994d37c99647c72feb8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltservicecertificategt"></a>&lt;serviceCertificate&gt;
Consente di configurare il certificato x. 509 utilizzato per crittografare e decrittografare i token.  
  
 \<System >  
\<federationConfiguration >  
\<serviceCertificate >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuna  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<certificateReference >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|Specifica le impostazioni che consentono di trovare e convalidare un certificato x. 509 nell'archivio certificati.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Contiene le impostazioni che configurano il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrato come utilizzare il \<serviceCertificate > elemento. Il codice XML viene prelevato il `CustomToken` esempio.  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
