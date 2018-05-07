---
title: '&lt;transport&gt; di &lt;ws2007HttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 3be9d4e64e63b32156cb64257f5bed8230cee3aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a>&lt;transport&gt; di &lt;ws2007HttpBinding&gt;
Definisce le impostazioni di autenticazione per il trasporto HTTP.  
  
 \<system.serviceModel>  
\<le associazioni >  
\<ws2007HttpBinding>  
\<binding>  
\<security>  
\<trasporto >  
  
## <a name="syntax"></a>Sintassi  
  
```  
transport clientCredentialType =   
       "Basic/Certificate/Digest/None/Ntlm/Windows"  
       proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
       realm="string"   
```  
  
## <a name="type"></a>Tipo  
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
  
|Valore|Descrizione|  
|-----------|-----------------|  
|None|La sicurezza è disabilitata.|  
|Di base|Usa l'autenticazione di base.|  
|Digest|Usa l'autenticazione digest.|  
|Ntlm|Usa l'autenticazione NTLM come fallback con un dominio Windows.|  
|Windows|Usa l'autenticazione integrata di Windows.|  
|Certificato|Usa certificati X.509 per autenticare il client.|  
  
## <a name="proxycredentialtype-attribute"></a>Attributo proxyCredentialType  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|None|La sicurezza è disabilitata.|  
|Di base|Usa l'autenticazione di base.|  
|Digest|Usa l'autenticazione digest.|  
|Ntlm|Usa NTLM come fallback con un dominio Windows.|  
|Windows|Usa l'autenticazione integrata di Windows.|  
|Certificato|Usa certificati X.509 per autenticare il client.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|Rappresenta le funzionalità di sicurezza di [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) elemento.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>  
 [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Uso di associazioni per configurare i client e servizi Windows Communication Foundation](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
