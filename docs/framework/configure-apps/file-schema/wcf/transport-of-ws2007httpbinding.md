---
title: <transport> di <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: ce8b2acb7d87b094958e20ca0b6cca9fc8266a8d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911979"
---
# <a name="transport-of-ws2007httpbinding"></a>\<> di trasporto \<di WS2007HttpBinding >
Definisce le impostazioni di autenticazione per il trasporto HTTP.  
  
 \<system.serviceModel>  
\<Binding >  
\<ws2007HttpBinding>  
\<binding>  
\<security>  
\<> di trasporto  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a>Type  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`clientCredentialType`|Specifica la credenziale usata per autenticare il client presso il servizio. L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.|  
|`proxyCredentialType`|Specifica la credenziale usata per autenticare il client presso un proxy di dominio. L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|`realm`|L'area di autenticazione per l'autenticazione di base o digest. Il valore predefinito è una stringa vuota.<br /><br /> L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione. Può inoltre specificare una raccolta di utenti aventi diritto di accesso. Un utente può eseguire una query nell'area di autenticazione per determinare quale dei vari possibili nomi utente e password possono essere usati.|  
  
## <a name="clientcredentialtype-attribute"></a>Attributo clientCredentialType  
  
|Value|DESCRIZIONE|  
|-----------|-----------------|  
|Nessuna|La sicurezza è disabilitata.|  
|Basic|Usa l'autenticazione di base.|  
|Digest|Usa l'autenticazione digest.|  
|Ntlm|Usa l'autenticazione NTLM come fallback con un dominio Windows.|  
|Windows|Usa l'autenticazione integrata di Windows.|  
|Certificato|Usa certificati X.509 per autenticare il client.|  
  
## <a name="proxycredentialtype-attribute"></a>Attributo proxyCredentialType  
  
|Value|DESCRIZIONE|  
|-----------|-----------------|  
|Nessuna|La sicurezza è disabilitata.|  
|Basic|Usa l'autenticazione di base.|  
|Digest|Usa l'autenticazione digest.|  
|Ntlm|Usa NTLM come fallback con un dominio Windows.|  
|Windows|Usa l'autenticazione integrata di Windows.|  
|Certificato|Usa certificati X.509 per autenticare il client.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](security-of-ws2007httpbinding.md)|Rappresenta le funzionalità di sicurezza dell' [ \<elemento > WS2007HttpBinding](ws2007httpbinding.md) .|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [Protezione di servizi e client](../../../wcf/feature-details/securing-services-and-clients.md)
- [Associazioni](../../../wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
