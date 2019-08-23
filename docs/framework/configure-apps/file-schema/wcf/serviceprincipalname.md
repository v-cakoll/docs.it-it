---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 28ae27481ea9cb86c31b5be1f12b5491f8ca143e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936162"
---
# <a name="serviceprincipalname"></a>\<servicePrincipalName>
Specifica l'identità di un servizio in base al relativo nome dell'entità servizio (SPN, Service Principal Name).  
  
 Per ulteriori informazioni sull'impostazione del nome SPN, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).  
  
 \<identity>  
\<servicePrincipalName>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|value|Nome in base al quale un client identifica in modo univoco un'istanza di un servizio. Se si installano più istanze di un servizio in computer distribuiti in una foresta, a ogni istanza deve essere associato un nome SPN distinto. Se i client possono usare più nomi per l'autenticazione, una determinata istanza di servizio può presentare più SPN.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identity>](identity.md)|Specifica l'identità del servizio da autenticare presso il client.|  
  
## <a name="remarks"></a>Note  
 Un client Windows Communication Foundation protetto (WCF) che si connette a un endpoint con questa identità usa il nome SPN quando esegue l'autenticazione SSPI con l'endpoint.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [Identità del servizio e autenticazione](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
