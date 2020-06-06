---
title: <message> di <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 75101744-eed8-4d61-91f4-5fc4473a21f2
ms.openlocfilehash: aef03634ed6156d3a7e052ccdbde35fdfda99cc3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736734"
---
# <a name="message-of-wsdualhttpbinding"></a>\<message> di \<wsDualHttpBinding>
Definisce la sicurezza a livello di messaggio per l'oggetto [\<wsDualHttpBinding>](wsdualhttpbinding.md) .  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
         negotiateServiceCredential="Boolean"
         algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
</message>
```  
  
## <a name="type"></a>Tipo  
 <xref:System.ServiceModel.MessageSecurityOverHttp>  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|algorithmSuite|Facoltativa. Imposta la crittografia dei messaggi e gli algoritmi di incapsulamento della chiave. Gli algoritmi e le dimensioni della chiave sono determinati dalla classe <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>. Questi algoritmi sono associati a quelli indicati nella specifica Security Policy Language (WS-SecurityPolicy).<br /><br /> Di seguito sono riportati i valori possibili. Il valore predefinito è `Basic256`.|  
|clientCredentialType|Facoltativa. Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita usando la modalità di sicurezza `Message`. Di seguito sono riportati i valori possibili. Il valore predefinito è `Windows`.<br /><br /> L'attributo è di tipo <xref:System.ServiceModel.MessageCredentialType>.|  
|negotiateServiceCredential|Facoltativa. Valore booleano che specifica se viene eseguito il provisioning della credenziale del servizio al client fuori banda o se viene ottenuta dal servizio al client tramite un processo di negoziazione. Tale negoziazione precede lo scambio di messaggi abituale.<br /><br /> Se l' `clientCredentialType` attributo è uguale a None, username o certificate, l'impostazione di questo attributo su `false` implica che il certificato del servizio sia disponibile nel client fuori banda e che il client debba specificare il certificato del servizio (mediante [\<serviceCertificate>](servicecertificate-of-servicecredentials.md) ) nel [\<serviceCredentials>](servicecredentials.md) comportamento del servizio. Questa modalità è interoperabile con gli stack SOAP che implementano WS-Trust e WS-SecureConversation.<br /><br /> Se l'attributo `ClientCredentialType` è impostato su `Windows`, l'impostazione di questo attributo su `false` specifica l'autenticazione basata su Kerberos. Questo significa che il client e il servizio devono fare parte dello stesso dominio Kerberos. Questa modalità è interoperabile con gli stack SOAP che implementano il profilo del token Kerberos (come definito in OASIS WSS TC) e anche WS-Trust e WS-SecureConversation. Quando questo attributo è `true`, si verifica una negoziazione SOAP .NET che esegue il tunneling dello scambio SPNego su messaggi SOAP.<br /><br /> Il valore predefinito è `true`.|  
  
## <a name="algorithmsuite-attribute"></a>Attributo algorithmSuite  
  
|Valore|Description|  
|-----------|-----------------|  
|Basic128|Usa crittografia Aes128, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|Basic192|Usa crittografia Aes192, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|Basic256|Usa crittografia Aes256, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|Basic256Rsa15|Usa Aes256 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
|Basic192Rsa15|Usa Aes192 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
|TripleDes|Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|Basic128Rsa15|Usa crittografia Aes128, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
|TripleDesRsa15|Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
|Basic128Sha256|Usa crittografia Aes256, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|Basic192Sha256|Usa Aes192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|Basic256Sha256|Usa crittografia Aes256, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|TripleDesSha256|Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|Basic128Sha256Rsa15|Usa Aes128 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
|Basic192Sha256Rsa15|Usa Aes192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
|Basic256Sha256Rsa15|Usa Aes256 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
|TripleDesSha256Rsa15|Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
  
## <a name="clientcredentialtype-attribute"></a>Attributo clientCredentialType  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|nessuno|None: consente al servizio di interagire con i client anonimi. Sul lato del servizio, indica che il servizio non richiede alcuna credenziale client. Sul client, indica che il client non fornisce alcuna credenziale client.|  
|Windows|consente lo svolgimento degli scambi SOAP nel contesto autenticato di una credenziale di Windows. Se l'attributo `negotiateServiceCredential` è impostato su `true`, esegue una negoziazione SSPI o Kerberos (un standard interoperabile).|  
|UserName|Consente al servizio di richiedere che l'autenticazione del client sia eseguita tramite una credenziale UserName. WCF non supporta l'invio del digest di una password né la derivazione di chiavi mediante una password e l'utilizzo di tali chiavi per la sicurezza dei messaggi. Di conseguenza, WCF impone che il trasporto sia protetto quando si utilizzano le credenziali del nome utente. Questa modalità di credenziale produce un scambio interoperabile o una negoziazione non interoperabile basata sull'attributo `negotiateServiceCredential`.|  
|Certificato|Consente al servizio di richiedere che l'autenticazione del client si basi su un certificato. Se viene usata la modalità di sicurezza del messaggio e l'attributo `negotiateServiceCredential` è impostato su `false`, è necessario eseguire il provisioning del client tramite il certificato del servizio.|  
|IssuedToken|Specifica un token personalizzato, generalmente rilasciato da un servizio di token di sicurezza.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](security-of-wsdualhttpbinding.md)|Definisce le funzionalità di sicurezza di [\<wsDualHttpBinding>](wsdualhttpbinding.md) .|  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSDualHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>
- <xref:System.ServiceModel.MessageSecurityOverHttp>
- [Securing Services and Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Binding](../../../wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
