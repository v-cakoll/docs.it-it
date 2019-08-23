---
title: <add> di <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 65398c5afa9750f215c95899bb6004cae671123a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920265"
---
# <a name="add-of-authorizationpolicies"></a>\<aggiungere > di \<AuthorizationPolicies >
Specifica i criteri di autorizzazione per la trasformazione di attestazioni.  
  
 \<system.ServiceModel>  
\<comportamenti >  
\<comportamento >  
\<serviceAuthorization>  
\<authorizationPolicies>  
\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a>Type  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|`policyType`|Attributo stringa obbligatorio.<br /><br /> Il modello di controllo di accesso Windows Communication Foundation (WCF) supporta il provisioning di un set di criteri di autorizzazione come tipi. Questo attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni. Su questa base può essere concesso o negato il controllo di accesso.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<authorizationPolicies>](authorizationpolicies.md)|Specifica una raccolta di tipi di criteri di autorizzazione.|  
  
## <a name="remarks"></a>Note  
 Ciascun criterio di autorizzazione contiene un solo attributo `policyType` obbligatorio che è una stringa. L'attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni. Su questa base può essere concesso o negato il controllo di accesso. Per ulteriori informazioni sul funzionamento di un criterio di autorizzazione, <xref:System.IdentityModel.Policy.IAuthorizationPolicy> vedere e [criteri di autorizzazione](../../../wcf/samples/authorization-policy.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [Autorizzazione dell'accesso alle operazioni del servizio](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [Procedura: Creazione di un gestore autorizzazioni personalizzato per un servizio](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [\<add>](add-of-authorizationpolicies.md)
- [Criteri di autorizzazione](../../../wcf/samples/authorization-policy.md)
