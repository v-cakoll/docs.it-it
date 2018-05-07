---
title: '&lt;message&gt; di &lt;ws2007HttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 9ffd8db6-84a8-4b38-a9fe-2cb1a87a1c97
ms.openlocfilehash: 39d5ce66537fd6c94895205ccc855d7fb631284e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ltmessagegt-of-ltws2007httpbindinggt"></a>&lt;message&gt; di &lt;ws2007HttpBinding&gt;
Definisce le impostazioni per la sicurezza a livello di messaggio di [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) elemento.  
  
 \<system.ServiceModel>  
\<le associazioni >  
\<ws2007HttpBinding>  
\<binding>  
\<security>  
\<messaggio >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<ws2007HttpBinding>  
 <binding >  
  <security>  
   <message clientCredentialType =  
    "None/Windows/UserName/Certificate/IssuedToken"  
    establishSecurityContext="Boolean"  
    negotiateServiceCredential="Boolean"  
    algorithmSuite= Enumeration. See algorithmSuite Attribute below.  
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
|`algorithmSuite`|Imposta la crittografia dei messaggi e gli algoritmi di incapsulamento della chiave. Gli algoritmi e le dimensioni della chiave sono determinati dalla classe <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>. Questi algoritmi sono associati a quelli specificati nelle specifiche del linguaggio dei criteri di sicurezza (WS-SecurityPolicy).<br /><br /> Il valore predefinito è Basic256.|  
|`clientCredentialType`|Parametro facoltativo. Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita usando la modalità di sicurezza `Message` o `TransportWithMessageCredentials`. Vedere i valori di enumerazione elencati nella tabella seguente. L'impostazione predefinita è Windows.<br /><br /> L'attributo è di tipo <xref:System.ServiceModel.MessageCredentialType>.|  
|`establishSecurityContext`|Valore che determina se il canale di sicurezza stabilisce una sessione protetta. Una sessione protetta stabilisce un token del contesto di sicurezza prima di scambiare i messaggi dell'applicazione. Quando il token del contesto di sicurezza è stabilito, il canale di sicurezza offre un'interfaccia <xref:System.ServiceModel.Channels.ISession> ai canali superiori. Per ulteriori informazioni sull'utilizzo di sessioni protette, vedere [procedura: creare una sessione protetta](../../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md).<br /><br /> Il valore predefinito è `true`.|  
|`negotiateServiceCredential`|Parametro facoltativo. Valore che specifica se viene eseguito il provisioning della credenziale del servizio al client fuori banda o se viene ottenuta dal servizio al client tramite un processo di negoziazione. Tale negoziazione precede lo scambio di messaggi abituale.<br /><br /> Se il `clientCredentialType` attributo è uguale a None, nome utente o certificato, impostare questo attributo su `false` implica che il certificato del servizio sia disponibile nel client fuori banda e che il client deve specificare il certificato del servizio (tramite il [ \<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) nei [ \<serviceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) comportamento del servizio. Questa modalità è interoperativa con gli stack SOAP che implementano WS-Trust e WS-SecureConversation.<br /><br /> Se l'attributo `ClientCredentialType` è impostato su `Windows`, l'impostazione di questo attributo su `false` specifica l'autenticazione basata su Kerberos. Questo significa che il client e il servizio devono fare parte dello stesso dominio Kerberos. Questa modalità è interoperativa con gli stack SOAP che implementano il profilo del token Kerberos (come definito in OASIS WSS TC) nonché WS-Trust e WS-SecureConversation.<br /><br /> Quando questo attributo è `true`, si verifica una negoziazione SOAP .NET che esegue il tunneling dello scambio <xref:System.ServiceModel.Security.Tokens.ServiceModelSecurityTokenTypes.Spnego%2A> su messaggi SOAP.<br /><br /> Il valore predefinito è `true`.|  
  
## <a name="algorithmsuite-attribute"></a>Attributo algorithmSuite  
  
|Valore|Descrizione|  
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
|`None`|None: consente al servizio di interagire con i client anonimi. Sul servizio, indica che il servizio non richiede alcuna credenziale client. Sul client, indica che il client non fornisce alcuna credenziale client.|  
|`Certificate`|Consente al servizio di richiedere che l'autenticazione del client si basi su un certificato. Se viene usata la modalità di sicurezza `message` e l'attributo `negotiateServiceCredential` è impostato su `false`, è necessario eseguire il provisioning del client tramite il certificato del servizio.|  
|`IssuedToken`|Specifica un token personalizzato, emesso da un servizio di token di sicurezza.|  
|`UserName`|Consente al servizio di richiedere che l'autenticazione del client si basi su una credenziale `UserName`. WCF non supporta l'invio di un digest delle password, né la derivazione delle chiavi password e l'uso di tali chiavi per la sicurezza del messaggio. Di conseguenza, WCF richiede che il trasporto sia protetto quando si utilizza `UserName` credenziali. Questa modalità di credenziale produce un scambio interoperabile o una negoziazione non interoperabile basata sull'attributo `negotiateServiceCredential`.|  
|`Windows`|Consente lo svolgimento degli scambi SOAP nel contesto autenticato di una credenziale `Windows`. Se l'attributo `negotiateServiceCredential` è impostato su `true`, esegue una negoziazione SSPI o Kerberos (un standard interoperabile).|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|Definisce le impostazioni di sicurezza per un [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md).|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Message%2A>  
 <xref:System.ServiceModel.Configuration.NonDualMessageSecurityOverHttpElement>  
 [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Uso di associazioni per configurare i client e servizi Windows Communication Foundation](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
