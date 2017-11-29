---
title: '&lt;userPrincipalName&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b93a0cc24953024e265df418ec6dd738598dd0f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltuserprincipalnamegt"></a>&lt;userPrincipalName&gt;
Specifica il nome principale dell'utente (UPN, User Principal Name) di un servizio da autenticare presso il client.  
  
 Per ulteriori informazioni sull'impostazione l'UPN, vedere [autenticazione e identità del servizio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
\<identità >  
\<userPrincipalName >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<userPrincipalName value="String" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|predefinito|Nome costituito dal nome dell'account utente (talvolta detto nome di accesso utente) e dal nome del dominio in cui tale account si trova. Questo nome rappresenta il formato standard dei nomi di accesso a un dominio Windows. Il formato è: someone@example.com (per un indirizzo di posta elettronica).|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identità >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Specifica l'identità del servizio da autenticare presso il client.|  
  
## <a name="remarks"></a>Note  
 Un client [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] protetto che si connette a un endpoint con questa identità usa l'UPN quando esegue l'autenticazione SSPI con l'endpoint.  
  
## <a name="example"></a>Esempio  
 Il codice di configurazione seguente specifica il nome UPN del servizio da autenticare presso il client.  
  
```xml  
<identity>  
  <userPrincipalName value="someone@cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.UpnEndpointIdentity>  
 [L'autenticazione e identità del servizio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [\<identità >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
