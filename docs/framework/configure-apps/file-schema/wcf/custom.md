---
title: '&lt;custom&gt;'
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 7d558be66b8a1e46d9743c5f8bf0bb9a8b4c349e
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48036833"
---
# <a name="ltcustomgt"></a>&lt;custom&gt;
Specifica le impostazioni di un servizio resolver peer personalizzato.  
  
\<system.serviceModel>  
\<le associazioni >  
\<netPeerBinding>  
\<binding>  
\<resolver >  
\<custom>  
  
## <a name="syntax"></a>Sintassi  
  
```xml
<custom address="Uri" 
        resolverType="String">  
  <headers/>  
  <identity/>  
</custom>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`address`|URI che specifica l'indirizzo dell'endpoint del nodo peer che ospita il servizio resolver peer personalizzato.|  
|`resolverType`|Stringa che specifica il tipo del servizio resolver peer personalizzato.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identità >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Specifica l'identità dei resolver peer personalizzati configurati per questo elemento. L'elemento è di tipo <xref:System.ServiceModel.Configuration.IdentityElement>.|  
|[\<intestazioni >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Raccolta di intestazioni di indirizzo usate per i messaggi SOAP gestiti dal resolver peer personalizzato.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<resolver>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|Resolver peer usato per risolvere un ID della rete di peer in un set di indirizzi di nodo peer che rappresenta alcuni nodi appartenenti alla rete.|  
  
## <a name="remarks"></a>Note  
 Questo elemento definisce le impostazioni di base per un servizio resolver peer personalizzato, inclusi l'indirizzo dell'endpoint del peer che ospita il servizio e le impostazioni dell'associazione specifiche. Per altre informazioni sulla creazione di un resolver personalizzato, vedere [aggiunta di un Resolver personalizzato a un'applicazione PeerChannel](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>  
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>  
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>  
 [Resolver del peer](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [Aggiunta di un Resolver personalizzato a un'applicazione PeerChannel](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
