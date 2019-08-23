---
title: <message> di <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: 4a7606c0ebc9fc1bbd34aef619dcb4b8a1d63fa5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931548"
---
# <a name="message-of-nethttpbinding"></a>\<> del messaggio \<di NetHttpBinding >
Definisce le impostazioni per la [ \<](basichttpbinding.md)sicurezza a livello di messaggio del > BasicHttpBinding.  
  
 \<system.ServiceModel>  
\<Binding >  
\<netHttpBinding>  
\<binding>  
\<security>  
\<> messaggi  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|algorithmSuite|Imposta la crittografia dei messaggi e gli algoritmi di incapsulamento della chiave. L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, che specifica gli algoritmi e le dimensioni della chiave. Questi algoritmi sono associati a quelli specificati nelle specifiche del linguaggio dei criteri di sicurezza (WS-SecurityPolicy).<br /><br /> Il valore predefinito è `Basic256`.|  
|clientCredentialType|Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita usando la sicurezza basata sul messaggio. Il valore predefinito è `UserName`.|  
  
## <a name="clientcredentialtype-attribute"></a>Attributo clientCredentialType  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|UserName|-Richiede che il client venga autenticato nel server con una credenziale UserName. Questa credenziale deve essere specificata tramite l'elemento`clientCredentials`< >.<br />-WCF non supporta l'invio di un digest della password o la derivazione di chiavi tramite password e l'utilizzo di tali chiavi per la sicurezza dei messaggi. Pertanto, WCF impone che il trasporto sia protetto quando si utilizzano le credenziali del nome utente. Per `basicHttpBinding`, questo richiede l'impostazione di un canale SSL.|  
|Certificato|Richiede che l'autenticazione del client sul server avvenga mediante un certificato. La credenziale client in questo caso deve essere specificata usando <`clientCredentials`> e il <`clientCertificate`>. Inoltre, quando si usa la modalità di sicurezza del messaggio, è necessario eseguire il provisioning del client con il certificato del servizio. In questo caso la credenziale del servizio deve essere specificata <xref:System.ServiceModel.Description.ClientCredentials> tramite l' `ClientCredentials` elemento Class o Behavior e specificando il certificato \<di servizio mediante l'elemento serviceCertificate > di ServiceCredentials.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|<`security`elemento > di <`netHttpBinding`>|Definisce le funzionalità di sicurezza per l'`netHttpBinding`elemento < >.|  
  
## <a name="example"></a>Esempio  
 In questo esempio viene dimostrato come implementare un'applicazione che usa basicHttpBinding e la sicurezza del messaggio. Nel seguente esempio di configurazione di un servizio, la definizione dell'endpoint specifica basicHttpBinding e fa riferimento a una configurazione di associazione denominata `Binding1`. Il certificato usato dal servizio per l'autenticazione con il client è impostato nella sezione `behaviors` del file di configurazione sotto l'elemento `serviceCredentials`. Anche la modalità di convalida applicata al certificato usato dal servizio per l'autenticazione con il client è impostata nella sezione `behaviors` del file di configurazione sotto l'elemento `clientCertificate`.  
  
 Gli stessi dettagli sull'associazione e la sicurezza sono specificati nel file di configurazione del client.  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
      <!-- This configuration defines the SecurityMode as Message and
           the clientCredentialType as Certificate. -->
      <binding name="Binding1" >
        <security mode = "Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True" />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <!-- The serviceCredentials behavior allows one to define a service certificate.
             A service certificate is used by a client to authenticate the service and provide message protection.
             This configuration references the "localhost" certificate installed during the setup instructions. -->
        <serviceCredentials>
          <serviceCertificate findValue="localhost"
                              storeLocation="LocalMachine"
                              storeName="My"
                              x509FindType="FindBySubjectName" />
          <clientCertificate>
            <!-- Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
                 is in the user's Trusted People store, then it will be trusted without performing a
                 validation of the certificate's issuer chain. This setting is used here for convenience so that the
                 sample can be run without having to have certificates issued by a certification authority (CA).
                 This setting is less secure than the default, ChainTrust. The security implications of this
                 setting should be carefully considered before using PeerOrChainTrust in production code. -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a>Vedere anche

- [Protezione di servizi e client](../../../wcf/feature-details/securing-services-and-clients.md)
- [Associazioni](../../../wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
