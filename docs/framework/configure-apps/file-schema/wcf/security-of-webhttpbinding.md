---
title: <security> di <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 806cf8524ed1a1439ca85a4b918e8e486e5dc94b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936592"
---
# <a name="security-of-webhttpbinding"></a>\<> di sicurezza \<di WebHttpBinding >
Specifica i requisiti di sicurezza per un endpoint configurato con un [ \<> WebHttpBinding](webhttpbinding.md).  
  
 \<system.ServiceModel>  
\<Binding >  
\<webHttpBinding>  
\<binding>  
\<security>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.ServiceModel>
  <bindings>
    <webHttpBinding>
      <binding name = "String">
        <security mode="None/Transport/TransportCredentialOnly">
          <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                     realm="String" />
        </security>
      </binding>
    </webHttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|modalità|Consente di specificare se un endpoint usa la sicurezza a livello di trasporto o se non usa alcuna sicurezza. Il valore predefinito è `None`. L'attributo è di tipo <xref:System.ServiceModel.WebHttpSecurityMode>.|  
  
## <a name="mode-attribute"></a>Attributo mode  
  
|Value|DESCRIZIONE|  
|-----------|-----------------|  
|Nessuna|La sicurezza è disabilitata.|  
|Trasporto|La sicurezza è fornita mediante HTTPS. Può essere necessario che il servizio sia configurato con certificati SSL. Il messaggio è interamente protetto usando HTTPS e il servizio viene autenticato dal client usando il certificato SSL del servizio. L'autenticazione client viene controllata tramite l' `ClientCredentialType` attributo [ \<del > di trasporto](transport-of-webhttpbinding.md).|  
|TransportCredentialOnly|Questa modalità non fornisce l'integrità e la riservatezza dei messaggi, ma fornisce l'autenticazione client basata su HTTP. Tale modalità deve essere usata con cautela. Deve essere utilizzato in ambienti in cui la sicurezza del trasporto viene fornita tramite altri mezzi (ad esempio IPSec) e l'infrastruttura WCF fornisce solo l'autenticazione client.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<transport>](transport-of-webhttpbinding.md)|Definisce le impostazioni di sicurezza del trasporto. Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<webHttpBinding>](webhttpbinding.md)|Elemento di associazione utilizzato per configurare endpoint per i servizi Web di Windows Communication Foundation (WCF) che rispondono a richieste HTTP anziché a messaggi SOAP.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [Protezione di servizi e client](../../../wcf/feature-details/securing-services-and-clients.md)
- [Selezione di un tipo di credenziale](../../../wcf/feature-details/selecting-a-credential-type.md)
- [Associazioni](../../../wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
- [Modello di programmazione HTTP Web di WCF](../../../wcf/feature-details/wcf-web-http-programming-model.md)
