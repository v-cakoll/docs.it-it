---
title: <transport> di <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: e8016eb9058f132722587368f1f8c7c03220af4a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732796"
---
# <a name="transport-of-webhttpbinding"></a>\<transport> di \<webHttpBinding>
Definisce le impostazioni di sicurezza a livello di trasporto per un endpoint del servizio configurato per ricevere richieste HTTP.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<webHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</webHttpBinding>
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
|`realm`|Stringa che specifica l'area di autenticazione per l'autenticazione di base o digest. Il valore predefinito è una stringa vuota.<br /><br /> L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione. Può inoltre specificare una raccolta di utenti aventi diritto di accesso. Un utente può eseguire una query nell'area di autenticazione per verificare i nomi utente e le password da usare tra quelli possibili.|  
|`policyEnforcement`|Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.<br /><br /> 1. Never: il criterio non viene mai applicato (la protezione estesa è disabilitata).<br />2. WhenSupported: i criteri vengono applicati solo se il client supporta la protezione estesa.<br />3. always: i criteri vengono sempre applicati. L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.|  
  
## <a name="clientcredentialtype-attribute"></a>Attributo clientCredentialType  
  
|Valore|Description|  
|-----------|-----------------|  
|`None`|La sicurezza è disabilitata.|  
|`Basic`|Usa l'autenticazione di base.|  
|`Certificate`|Usa certificati X.509 per autenticare il client.|  
|`Digest`|Usa l'autenticazione digest.|  
|`Ntlm`|Usa l'autenticazione NTLM come fallback con un dominio Windows.|  
|`Windows`|Usa l'autenticazione integrata di Windows.|  
  
## <a name="proxycredentialtype-attribute"></a>Attributo proxyCredentialType  
  
|Valore|Description|  
|-----------|-----------------|  
|`None`|La sicurezza è disabilitata.|  
|`Basic`|Usa l'autenticazione di base.|  
|`Digest`|Usa l'autenticazione digest.|  
|`Ntlm`|Usa NTLM come fallback con un dominio Windows.|  
|`Windows`|Usa l'autenticazione integrata di Windows.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](security-of-webhttpbinding.md)|Rappresenta le funzionalità di sicurezza dell' [\<wsHttpBinding>](wshttpbinding.md) elemento.|  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [Securing Services and Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Binding](../../../wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [Modello di programmazione HTTP Web WCF](../../../wcf/feature-details/wcf-web-http-programming-model.md)
