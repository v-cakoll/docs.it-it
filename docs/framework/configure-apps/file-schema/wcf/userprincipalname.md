---
title: '&lt;userPrincipalName&gt;'
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 1bb0c8ac4cbe11cdfa31beb16b00b3863acabf92
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358677"
---
# <a name="ltuserprincipalnamegt"></a>&lt;userPrincipalName&gt;
Specifica il nome principale dell'utente (UPN, User Principal Name) di un servizio da autenticare presso il client.  
  
 Per ulteriori informazioni sull'impostazione l'UPN, vedere [autenticazione e identità del servizio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
\<identità >  
\<userPrincipalName>  
  
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
 Un client protetto di Windows Communication Foundation (WCF) che si connette a un endpoint con questa identità usa l'UPN quando esegue l'autenticazione SSPI con l'endpoint.  
  
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
 [Identità del servizio e autenticazione](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [\<identità >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
