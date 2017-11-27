---
title: '&lt;servicePrincipalName&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e472c7fcfd57341074489a75f7954be38291523b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltserviceprincipalnamegt"></a>&lt;servicePrincipalName&gt;
Specifica l'identità di un servizio in base al relativo nome dell'entità servizio (SPN, Service Principal Name).  
  
 Per ulteriori informazioni sull'impostazione del nome SPN, vedere [autenticazione e identità del servizio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
 \<identità >  
\<servicePrincipalName >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<servicePrincipalName value = "String" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|predefinito|Nome in base al quale un client identifica in modo univoco un'istanza di un servizio. Se si installano più istanze di un servizio in computer distribuiti in una foresta, a ogni istanza deve essere associato un nome SPN distinto. Se i client possono usare più nomi per l'autenticazione, una determinata istanza di servizio può presentare più SPN.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identità >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Specifica l'identità del servizio da autenticare presso il client.|  
  
## <a name="remarks"></a>Note  
 Un client [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] protetto che si connette a un endpoint con questa identità usa l'SPN quando esegue l'autenticazione SSPI con l'endpoint.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.SpnEndpointIdentity>  
 [L'autenticazione e identità del servizio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [\<identità >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
