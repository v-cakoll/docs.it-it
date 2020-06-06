---
title: <security> di <customBinding>
ms.date: 03/30/2017
ms.assetid: 243a5148-bbd1-447f-a8a5-6e7792c0a3f1
ms.openlocfilehash: 454113f66007ddd69f8455bb532e9cbd12fcefb7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738703"
---
# <a name="security-of-custombinding"></a>\<security> di \<customBinding>
Specifica le opzioni di sicurezza di un'associazione personalizzata.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<security allowSerializedSigningTokenOnReply="Boolean"
          authenticationMode="AuthenticationMode"
          defaultAlgorithmSuite="SecurityAlgorithmSuite"
          includeTimestamp="Boolean"
          requireDerivedKeys="Boolean"
          keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
          messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
          messageSecurityVersion="WSSecurityJan2004/WSSecurityXXX2005"
          requireDerivedKeys="Boolean"
          requireSecurityContextCancellation="Boolean"
          requireSignatureConfirmation="Boolean"
          securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast">
   <issuedTokenParameters />
   <localClientSettings />
   <localServiceSettings />
   <secureConversationBootstrap />
</security>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|allowSerializedSigningTokenOnReply|Facoltativa. Valore booleano che specifica se è possibile usare un token serializzato nella risposta. Il valore predefinito è `false`. Se si usa un'associazione duplice, l'impostazione assume `true` come valore predefinito e qualsiasi impostazione effettuata sarà ignorata.|  
|authenticationMode|Facoltativa. Specifica la modalità di autenticazione usata tra l'iniziatore e il risponditore. Di seguito sono riportati tutti i valori.<br /><br /> Il valore predefinito è `sspiNegotiated`.|  
|defaultAlgorithmSuite|Facoltativa. Imposta la crittografia dei messaggi e gli algoritmi di incapsulamento della chiave. Gli algoritmi e le dimensioni della chiave sono determinati dalla classe <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>. Questi algoritmi sono associati a quelli indicati nella specifica Security Policy Language (WS-SecurityPolicy).<br /><br /> I valori possibili sono riportati di seguito. Il valore predefinito è `Basic256`.<br /><br /> Questo attributo viene usato con una piattaforma differente che usa un set di algoritmi diverso da quello predefinito. Quando si apportano modifiche a questa impostazione, è necessario essere consapevoli dei punti di forza e dei punti di debolezza degli algoritmi pertinenti. L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|  
|includeTimestamp|Valore booleano che specifica se in ogni messaggio vengono inclusi gli indicatori di data e ora. Il valore predefinito è `true`.|  
|keyEntropyMode|Specifica la modalità di calcolo delle chiavi per la sicurezza dei messaggi. Le chiavi possono essere basate solo sul materiale della chiave client, solo sul materiale della chiave del servizio o su una combinazione di entrambi. I valori validi sono:<br /><br /> -   `ClientEntropy`: La chiave della sessione si basa sui dati chiave forniti dal client.<br />-   `ServerEntropy`: La chiave della sessione si basa sui dati chiave forniti dal server.<br />-   `CombinedEntropy`: La chiave della sessione si basa sui dati chiave forniti dal client e dal servizio.<br /><br /> Il valore predefinito è `CombinedEntropy`.<br /><br /> L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.|  
|messageProtectionOrder|Imposta l'ordine nel quale gli algoritmi di sicurezza a livello di messaggio vengono applicati al messaggio. I valori validi sono i seguenti:<br /><br /> -   `SignBeforeEncrypt`: Prima firma, quindi crittografia.<br />-   `SignBeforeEncryptAndEncryptSignature`: Prima firmare, crittografare e crittografare la firma.<br />-   `EncryptBeforeSign`: Prima crittografia, quindi firma.<br /><br /> Il valore predefinito dipende dalla versione di WS-Security usata. Il valore predefinito è `SignBeforeEncryptAndEncryptSignature` quando si usa WS-Security 1,1. Il valore predefinito è `SignBeforeEncrypt` quando si usa WS-Security 1.0.<br /><br /> L'attributo è di tipo <xref:System.ServiceModel.Security.MessageProtectionOrder>.|  
|messageSecurityVersion|Facoltativa. Imposta la versione di WS-Security da usare. I valori validi sono i seguenti:<br /><br /> -WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11<br />-WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10<br />-WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10<br /><br /> L'impostazione predefinita è WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11 e può essere espressa in XML semplicemente come `Default`. L'attributo è di tipo <xref:System.ServiceModel.MessageSecurityVersion>.|  
|requireDerivedKeys|Valore booleano che specifica se le chiavi possono essere derivate dalle chiavi di prova originali. Il valore predefinito è `true`.|  
|requireSecurityContextCancellation|Facoltativa. Valore booleano che specifica se il contesto di sicurezza deve essere annullato e terminato quando non è più necessario. Il valore predefinito è `true`.|  
|requireSignatureConfirmation|Facoltativa. Valore booleano che specifica se la conferma della firma WS-Security è attivata. Quando è impostato su `true`, le firme del messaggio vengono confermate dal responder.  Quando l'associazione personalizzata è configurata per i certificati reciproci o per usare token rilasciati (associazioni WSS 1.1), questo attributo assume `true` come valore predefinito. Diversamente, il valore predefinito è `false`.<br /><br /> La conferma della firma è usata per confermare che la risposta del servizio sia completamente compatibile con una richiesta.|  
|securityHeaderLayout|Facoltativa. Specifica l'ordine degli elementi nell'intestazione di sicurezza. I valori validi sono:<br /><br /> -   `Strict`: Gli elementi vengono aggiunti all'intestazione di sicurezza in base al principio generale di "Declare before use".<br />-   `Lax`: Gli elementi vengono aggiunti all'intestazione di sicurezza in qualsiasi ordine che confermi a WSS: SOAP Message Security.<br />-   `LaxWithTimestampFirst`: Gli elementi vengono aggiunti all'intestazione di sicurezza in qualsiasi ordine che confermi a WSS: SOAP Message Security, ad eccezione del fatto che il primo elemento nell'intestazione di sicurezza deve essere un elemento elemento wsse: timestamp.<br />-   `LaxWithTimestampLast`: Gli elementi vengono aggiunti all'intestazione di sicurezza in qualsiasi ordine che conferma a WSS: SOAP Message Security, ad eccezione del fatto che l'ultimo elemento nell'intestazione di sicurezza deve essere un elemento elemento wsse: timestamp.<br /><br /> Il valore predefinito è `Strict`.<br /><br /> L'elemento è di tipo <xref:System.ServiceModel.Channels.SecurityHeaderLayout>.|  
  
## <a name="authenticationmode-attribute"></a>Attributo authenticationMode  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|string|`AnonymousForCertificate`<br /><br /> `AnonymousForSslNegotiated`<br /><br /> `CertificateOverTransport`<br /><br /> `IssuedToken`<br /><br /> `IssuedTokenForCertificate`<br /><br /> `IssuedTokenForSslNegotiated`<br /><br /> `IssuedTokenOverTransport`<br /><br /> `Kerberos`<br /><br /> `KerberosOverTransport`<br /><br /> `MutualCertificate`<br /><br /> `MutualCertificateDuplex`<br /><br /> `MutualSslNegotiated`<br /><br /> `SecureConversation`<br /><br /> `SspiNegotiated`<br /><br /> `UserNameForCertificate`<br /><br /> `UserNameForSslNegotiated`<br /><br /> `UserNameOverTransport`<br /><br /> `SspiNegotiatedOverTransport`|  
  
## <a name="defaultalgorithm-attribute"></a>Attributo defaultAlgorithm  
  
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
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|Specifica un token corrente rilasciato. L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>.|  
|[\<localClientSettings>](localclientsettings-element.md)|Specifica le impostazioni di sicurezza di un client locale per questa associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>.|  
|[\<localServiceSettings>](localservicesettings-element.md)|Specifica le impostazioni di sicurezza di un servizio locale per questa associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>.|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|Specifica i valori predefiniti usati per iniziare un servizio di conversazione protetta.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Definisce tutte le funzionalità di associazione dell'associazione personalizzata.|  
  
## <a name="remarks"></a>Commenti  
 Per altre informazioni sull'uso di questo elemento, vedere [modalità di autenticazione di SecurityBindingElement](../../../wcf/feature-details/securitybindingelement-authentication-modes.md) e [procedura: creare un'associazione personalizzata usando SecurityBindingElement](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente è dimostrato come configurare la sicurezza mediante un'associazione personalizzata. Viene mostrato come usare un'associazione personalizzata per abilitare la sicurezza a livello di messaggio insieme con un trasporto sicuro. Questo è utile quando è necessario un trasporto protetto per trasmettere i messaggi tra client e servizio e simultaneamente i messaggi devono essere protetti a livello di messaggio. Questa configurazione non è supportata dalle associazioni fornite dal sistema.  
  
 La configurazione del servizio definisce un'associazione personalizzato che supporta la comunicazione TCP protetta mediante il protocollo TLS/SSL e la sicurezza dei messaggi di Windows. L'associazione personalizzata usa un certificato del servizio per autenticare il servizio sul livello del trasporto e proteggere i messaggi durante la trasmissione tra client e servizio. Questa operazione viene eseguita dall' [\<sslStreamSecurity>](sslstreamsecurity.md) elemento di associazione. Il certificato del servizio è configurato mediante un comportamento del servizio.  
  
 L'associazione personalizzata usa inoltre la sicurezza dei messaggi con tipo di credenziale di Windows, che è il tipo di credenziale predefinito. Questa operazione viene eseguita dall'elemento di associazione di [sicurezza](security-of-custombinding.md) . Il client e il servizio vengono autenticati mediante la sicurezza a livello di messaggio se il meccanismo di autenticazione Kerberos è disponibile. Se il meccanismo di autenticazione Kerberos non è disponibile, viene usata l'autenticazione NTLM. NTLM autentica il client con il servizio, ma non autentica il servizio con il client. L'elemento di associazione di [sicurezza](security-of-custombinding.md) è configurato per utilizzare `SecureConversation` AuthenticationType, che comporta la creazione di una sessione di sicurezza nel client e nel servizio. Questa operazione è necessaria per consentire il funzionamento del contratto duplex del servizio. Per altre informazioni sull'esecuzione di questo esempio, vedere [sicurezza dell'associazione personalizzata](../../../wcf/samples/custom-binding-security.md).  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <!-- use following base address -->
            <add baseAddress="net.tcp://localhost:8000/ServiceModelSamples/Service"/>
          </baseAddresses>
        </host>
        <endpoint address=""
                  binding="customBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
        <!-- the mex endpoint is exposed at net.tcp://localhost:8000/ServiceModelSamples/service/mex -->
        <endpoint address="mex"
                  binding="mexTcpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <bindings>
      <!-- configure a custom binding -->
      <customBinding>
        <binding name="Binding1">
          <security authenticationMode="SecureConversation"
                    requireSecurityContextCancellation="true">
          </security>
          <textMessageEncoding messageVersion="Soap12WSAddressing10"
                               writeEncoding="utf-8" />
          <sslStreamSecurity requireClientCertificate="false" />
          <tcpTransport />
        </binding>
      </customBinding>
    </bindings>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata />
          <serviceDebug includeExceptionDetailInFaults="False" />
          <serviceCredentials>
            <serviceCertificate findValue="localhost"
                                storeLocation="LocalMachine"
                                storeName="My"
                                x509FindType="FindBySubjectName" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.SecurityElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Binding](../../../wcf/bindings.md)
- [Estensione delle associazioni](../../../wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [Procedura: creare un'associazione personalizzata usando SecurityBindingElement](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Sicurezza delle associazioni personalizzate](../../../wcf/samples/custom-binding-security.md)
