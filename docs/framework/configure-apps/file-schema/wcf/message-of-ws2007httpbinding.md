---
title: <message> di <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 9ffd8db6-84a8-4b38-a9fe-2cb1a87a1c97
ms.openlocfilehash: 3396f74f76d790759f4c32de2907607486701b1a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738952"
---
# <a name="message-of-ws2007httpbinding"></a>\<message> di \<ws2007HttpBinding>
Definisce le impostazioni per la sicurezza a livello di messaggio dell' [\<ws2007HttpBinding>](ws2007httpbinding.md) elemento.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<ws2007HttpBinding>
  <binding>
    <security>
      <message clientCredentialType="None/Windows/UserName/Certificate/IssuedToken"
               establishSecurityContext="Boolean"
               negotiateServiceCredential="Boolean"
               algorithmSuite="Enumeration. See algorithmSuite Attribute below."
               defaultProtectionLevel="None/Sign/EncryptionAndSign" />
    </security>
  </binding>
</ws2007HttpBinding>
```  
  
## <a name="type"></a>Tipo  
 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`algorithmSuite`|Imposta la crittografia dei messaggi e gli algoritmi di incapsulamento della chiave. Gli algoritmi e le dimensioni della chiave sono determinati dalla classe <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>. Questi algoritmi sono associati a quelli indicati nella specifica Security Policy Language (WS-SecurityPolicy).<br /><br /> Il valore predefinito è Basic256.|  
|`clientCredentialType`|Facoltativa. Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita usando la modalità di sicurezza `Message` o `TransportWithMessageCredentials`. Vedere i valori di enumerazione elencati nella tabella seguente. L'impostazione predefinita è Windows.<br /><br /> L'attributo è di tipo <xref:System.ServiceModel.MessageCredentialType>.|  
|`establishSecurityContext`|Valore che determina se il canale di sicurezza stabilisce una sessione protetta. Una sessione protetta stabilisce un token del contesto di sicurezza prima di scambiare i messaggi dell'applicazione. Quando il token del contesto di sicurezza è stabilito, il canale di sicurezza offre un'interfaccia <xref:System.ServiceModel.Channels.ISession> ai canali superiori. Per altre informazioni sull'uso di sessioni sicure, vedere [procedura: creare una sessione protetta](../../../wcf/feature-details/how-to-create-a-secure-session.md).<br /><br /> Il valore predefinito è `true`.|  
|`negotiateServiceCredential`|Facoltativa. Valore che specifica se viene eseguito il provisioning della credenziale del servizio al client fuori banda o se viene ottenuta dal servizio al client tramite un processo di negoziazione. Tale negoziazione precede lo scambio di messaggi abituale.<br /><br /> Se l' `clientCredentialType` attributo è uguale a None, username o certificate, l'impostazione di questo attributo su `false` implica che il certificato del servizio sia disponibile nel client fuori banda e che il client deve specificare il certificato del servizio (mediante [\<serviceCertificate>](servicecertificate-of-servicecredentials.md) ) nel [\<serviceCredentials>](servicecredentials.md) comportamento del servizio. Questa modalità è interoperativa con gli stack SOAP che implementano WS-Trust e WS-SecureConversation.<br /><br /> Se l'attributo `ClientCredentialType` è impostato su `Windows`, l'impostazione di questo attributo su `false` specifica l'autenticazione basata su Kerberos. Questo significa che il client e il servizio devono fare parte dello stesso dominio Kerberos. Questa modalità è interoperativa con gli stack SOAP che implementano il profilo del token Kerberos (come definito in OASIS WSS TC) nonché WS-Trust e WS-SecureConversation.<br /><br /> Quando questo attributo è `true`, si verifica una negoziazione SOAP .NET che esegue il tunneling dello scambio <xref:System.ServiceModel.Security.Tokens.ServiceModelSecurityTokenTypes.Spnego%2A> su messaggi SOAP.<br /><br /> Il valore predefinito è `true`.|  
  
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
  
|Valore|Description|  
|-----------|-----------------|  
|`None`|None: consente al servizio di interagire con i client anonimi. Sul servizio, indica che il servizio non richiede alcuna credenziale client. Sul client, indica che il client non fornisce alcuna credenziale client.|  
|`Certificate`|Consente al servizio di richiedere che l'autenticazione del client si basi su un certificato. Se viene usata la modalità di sicurezza `message` e l'attributo `negotiateServiceCredential` è impostato su `false`, è necessario eseguire il provisioning del client tramite il certificato del servizio.|  
|`IssuedToken`|Specifica un token personalizzato, emesso da un servizio di token di sicurezza.|  
|`UserName`|Consente al servizio di richiedere che l'autenticazione del client si basi su una credenziale `UserName`. WCF non supporta l'invio del digest di una password né la derivazione di chiavi mediante una password e l'utilizzo di tali chiavi per la sicurezza dei messaggi. Di conseguenza, WCF impone che il trasporto sia protetto quando si utilizzano le `UserName` credenziali. Questa modalità di credenziale produce un scambio interoperabile o una negoziazione non interoperabile basata sull'attributo `negotiateServiceCredential`.|  
|`Windows`|Consente lo svolgimento degli scambi SOAP nel contesto autenticato di una credenziale `Windows`. Se l'attributo `negotiateServiceCredential` è impostato su `true`, esegue una negoziazione SSPI o Kerberos (un standard interoperabile).|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](security-of-ws2007httpbinding.md)|Definisce le impostazioni di sicurezza per un oggetto [\<ws2007HttpBinding>](ws2007httpbinding.md) .|  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.NonDualMessageSecurityOverHttpElement>
- [Securing Services and Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Binding](../../../wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
