---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: a3aba5618855f7225dc8a427516eaa72b45f6e8b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942406"
---
# <a name="servicecertificate"></a>\<serviceCertificate>
Configura il certificato X. 509 usato per crittografare e decrittografare i token.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<serviceCertificate>  
  
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
|[\<certificateReference>](certificatereference.md)|Specifica le impostazioni utilizzate per individuare e convalidare un certificato X. 509 in un archivio certificati.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Contiene le impostazioni che configurano <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) <xref:System.IdentityModel.Services.SessionAuthenticationModule> e (Sam).|  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrato l'utilizzo \<dell'elemento > serviceCertificate. Il codice XML viene tratto dall' `CustomToken` esempio.  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
