---
title: Associazione HTTP WS 2007 Federation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91c1b477-a96e-4bf5-9330-5e9312113371
caps.latest.revision: "23"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a8ab75dea29196d956e1c2f7717d9008be12566
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ws-2007-federation-http-binding"></a>Associazione HTTP WS 2007 Federation
In questo esempio viene descritto l'utilizzo di <xref:System.ServiceModel.WS2007FederationHttpBinding>, un'associazione standard che è possibile utilizzare per compilare scenari federati che supportano la versione 1.3 della specifica WS-Trust.  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Questo esempio è costituito da un programma console (Client.exe), da un programma del servizio token di sicurezza basato su console (Securitytokenservice.exe) e da un programma di console del servizio (Service.exe). Il servizio implementa un contratto che definisce un modello di comunicazione request/reply. Il contratto viene definito dall'interfaccia `ICalculator` che espone operazioni matematiche (`Add`, `Subtract`, `Multiply` e `Divide`). Il client riceve un token di protezione dal servizio token di sicurezza (STS), esegue richieste sincrone al servizio per un'operazione matematica specificata. Il servizio risponde quindi fornendo il risultato. L'attività del client è visibile nella finestra della console.  
  
 L'esempio rende disponibile il contratto `ICalculator` utilizzando l'elemento `ws2007FederationHttpBinding`. La configurazione di quest'associazione sul client viene illustrata nel codice seguente.  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Endpoint address and binding for Security Token Service -->  
          <issuer address ="http://localhost:8000/sts/windows"   
                  binding ="ws2007HttpBinding" />                
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 Nel [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), `security` valore specifica la modalità di sicurezza deve essere utilizzata. In questo esempio, `message` viene utilizzata la sicurezza per questo motivo il [ \<messaggio >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) viene specificato all'interno di [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md). Il [ \<dell'autorità di certificazione >](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) elemento all'interno di [ \<messaggio >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifica l'indirizzo e l'associazione per il servizio token di sicurezza che rilascia un token di sicurezza per il client in modo che il client può eseguire l'autenticazione di `ICalculator` servizio.  
  
 La configurazione di quest'associazione sul servizio viene illustrata nel seguente codice.  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Metadata address for Security Token Service -->  
          <issuerMetadata address ="http://localhost:8000/sts/mex" >  
            <identity>  
              <certificateReference storeLocation ="CurrentUser"   
                                    storeName="TrustedPeople"   
                                    x509FindType ="FindBySubjectDistinguishedName"   
                                    findValue ="CN=STS" />  
            </identity>  
          </issuerMetadata>  
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 Nel [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), `security` valore specifica la modalità di sicurezza deve essere utilizzata. In questo esempio, `message` viene utilizzata la sicurezza per questo motivo il [ \<messaggio >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) viene specificato all'interno di [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md). Il [ \<issuerMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) elemento di `ws2007FederationHttpBinding` all'interno di [ \<messaggio >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifica l'indirizzo e l'identità di un endpoint che può essere utilizzato per recuperare metadati per il servizio token di sicurezza.  
  
 Il comportamento per il servizio viene illustrato nel codice seguente.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name ="ServiceBehaviour" >  
      <serviceDebug includeExceptionDetailInFaults ="true"/>  
      <serviceMetadata httpGetEnabled ="true"/>  
      <serviceCredentials>  
        <issuedTokenAuthentication>  
          <knownCertificates>  
            <add storeLocation ="LocalMachine"  
                 storeName="TrustedPeople"  
                 x509FindType="FindBySubjectDistinguishedName"  
                 findValue="CN=STS" />  
          </knownCertificates>  
        </issuedTokenAuthentication>  
        <serviceCertificate storeLocation ="LocalMachine"  
                            storeName ="My"  
                            x509FindType ="FindBySubjectDistinguishedName"  
                            findValue ="CN=localhost"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Il [ \<issuedTokenAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)> consente al servizio specificare i vincoli su token che i client possono presentare durante l'autenticazione. Questa configurazione specifica che i token firmati da un certificato il cui nome di soggetto è CN=STS possono essere accettati dal servizio.  
  
 Il servizio token di sicurezza rende disponibile un singolo endpoint utilizzando l'oggetto <xref:System.ServiceModel.WS2007HttpBinding> standard. Il servizio risponde alle richieste dei client per i token. Se il client viene autenticato utilizzando un account di Windows, il servizio pubblica un token che contiene il nome utente del client come attestazione. Come parte del processo di creazione del token, il servizio token di sicurezza firma il token utilizzando la chiave privata associata al certificato CN=STS . Crea, inoltre, una chiave simmetrica e la crittografa utilizzando la chiave pubblica associata al certificato CN=localhost. Nel restituire il token al client, il servizio token di sicurezza restituisce anche la chiave simmetrica. Il client presenta il token emesso al servizio `ICalculator` e dimostra che conosce la chiave simmetrica firmando il messaggio con quella chiave.  
  
 Quando si esegue l'esempio, la richiesta per il token di sicurezza viene visualizzata nella finestra della console del servizio token di sicurezza. Le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console del client e in quella del servizio. Premere INVIO in una delle finestre della console per arrestare l'applicazione.  
  
 `Add(100,15.99) = 115.99`  
  
 `Subtract(145,76.54) = 68.46`  
  
 `Multiply(9,81.25) = 731.25`  
  
 `Divide(22,7) = 3.14285714285714`  
  
 `Press <ENTER> to terminate client.`  
  
 Il file Setup.bat incluso in questo esempio consente di configurare il server e il servizio token di sicurezza con i certificati attinenti per eseguire un'applicazione indipendente. Il file batch crea due certificati, nell'archivio certificati di LocalMachine/TrustedPeople. Il primo certificato ha un nome soggetto di CN=STS e viene utilizzato dal servizio token di sicurezza per firmare i token di protezione emessi al client. Il secondo certificato ha un nome soggetto di CN=localhost e viene utilizzato dal servizio token di sicurezza per crittografare una chiave in modo che il servizio non possa decrittografarla.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Aprire un prompt dei comandi di Visual Studio con privilegi di amministratore ed eseguire Setup.bat per creare i certificati necessari.  
  
 Questo file batch utilizza Certmgr.exe e Makecert.exe, distribuiti con Windows SDK. È necessario tuttavia eseguire Setup.bat in un prompt dei comandi di Visual Studio per consentire allo script di trovare tali strumenti.  
  
1.  Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Per eseguire l'esempio in una configurazione a una o più computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md). Se si utilizza [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], è necessario eseguire Service.exe, Client.exe e SecurityTokenService.exe con privilegi elevati (fare clic sui file e quindi fare clic su **Esegui come amministratore**).  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\WS2007FederationHttp`  
  
## <a name="see-also"></a>Vedere anche
