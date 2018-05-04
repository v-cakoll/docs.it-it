---
title: '&lt;message&gt; di &lt;netMsmqBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: a552b0f22a79b30dcbbe1951906b121d4c5e8cf8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltmessagegt-of-ltnetmsmqbindinggt"></a>&lt;message&gt; di &lt;netMsmqBinding&gt;
Definisce le impostazioni di sicurezza dei messaggi SOAP in questa associazione `netMsmqBinding`.  
  
 \<system.ServiceModel>  
\<le associazioni >  
\<netMsmqBinding>  
\<binding>  
\<security>  
\<messaggio >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<netMsmqBinding>  
    <binding>  
      <security>  
         <message   
                      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
    </security>  
</netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|algorithmSuite|Imposta la crittografia del messaggio e gli algoritmi di incapsulamento della chiave usati per ottenere la sicurezza basata su messaggi per i messaggi inviati sul trasporto MSMQ.<br /><br /> Il valore predefinito è `Aes256`. L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|  
|clientCredentialType|Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita per i messaggi inviati sul trasporto MSMQ. Di seguito vengono elencati i valori validi:<br /><br /> -None: Consente al servizio di interagire con client anonimi. Né il servizio né il client richiedono una credenziale.<br />-Windows: Consente lo svolgimento degli scambi SOAP nel contesto autenticato di una credenziale di Windows. In questo caso viene sempre eseguita l'autenticazione basata su Kerberos.<br />-UserName: Consente al servizio di richiedere che il client venga autenticato tramite una credenziale UserName. In questo caso la credenziale deve essere specificata tramite il `clientCredentials` comportamento **attenzione:** Windows Communication Foundation (WCF) non supporta l'invio di una password digest né la derivazione delle chiavi usando la password e l'uso di tali chiavi per sicurezza dei messaggi. Di conseguenza, quando si usano le credenziali UserName, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] richiede che lo scambio sia protetto. Questa modalità richiede che sia specificato il certificato del servizio sul lato client mediante il comportamento `clientCredential` e `serviceCertificate`. <br /><br /> -Certificate: Consente al servizio di richiedere che il client venga autenticato tramite un certificato. La credenziale client in questo caso deve essere specificata tramite il comportamento `clientCredentials`. In questo caso la credenziale del servizio deve essere specificata usando il comportamento `clientCredentials` tramite la specifica di `serviceCertificate`.<br />-CardSpace: Consente al servizio di richiedere che il client venga autenticato tramite un CardSpace. Il provisioning del certificato `serviceCertiifcate` deve essere eseguito nel comportamento `clientCredential`.<br /><br /> Il valore predefinito è `Windows`. L'attributo è di tipo <xref:System.ServiceModel.MessageCredentialType>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|Definisce le impostazioni di sicurezza per un'associazione.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>  
 <xref:System.ServiceModel.MessageSecurityOverMsmq>  
 [Code in WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Uso di associazioni per configurare i client e servizi Windows Communication Foundation](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
