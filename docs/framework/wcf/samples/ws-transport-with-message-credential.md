---
title: Trasporto WS con credenziali del messaggio
ms.date: 03/30/2017
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
ms.openlocfilehash: 0082a9df5c112b66315236aad91bc891b80d27c7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596384"
---
# <a name="ws-transport-with-message-credential"></a>Trasporto WS con credenziali del messaggio
In questo esempio viene illustrato l'utilizzo della sicurezza del trasporto SSL in combinazione con l'inclusione delle credenziali client nel messaggio. In questo esempio viene usata l'associazione `wsHttpBinding`.  
  
 Per impostazione predefinita, l'associazione `wsHttpBinding` consente la comunicazione HTTP. Se viene configurata per la sicurezza del trasporto, l'associazione supporta la comunicazione HTTPS. Il protocollo HTTPS garantisce la riservatezza e l'integrità dei messaggi trasmessi in rete. Tuttavia il set di meccanismi di autenticazione che possono essere utilizzati per autenticare il client nel servizio è limitato ai meccanismi supportati dal trasporto HTTPS. Windows Communication Foundation (WCF) offre una `TransportWithMessageCredential` modalità di sicurezza progettata per ovviare a questa limitazione. Se è configurata questa modalità di sicurezza, viene utilizzata la sicurezza del trasporto per garantire la riservatezza e l'integrità dei messaggi trasmessi e per eseguire l'autenticazione del servizio. Tuttavia, l'autenticazione client viene eseguita inserendo la credenziale client direttamente nel messaggio. In questo modo è possibile utilizzare qualsiasi tipo di credenziale supportato dalla modalità di sicurezza dei messaggi per l'autenticazione del client, mantenendo i vantaggi a livello di prestazioni offerti dalla modalità di sicurezza del trasporto.  
  
 In questo esempio viene utilizzato un tipo di credenziale `UserName` per autenticare il client presso il servizio.  
  
 Questo esempio si basa sul [Introduzione](getting-started-sample.md) che implementa un servizio di calcolatrice. L'associazione `wsHttpBinding` è specificata e configurata nei file di configurazione dell'applicazione per il client e il servizio.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Il codice programma nell'esempio è quasi identico a quello del servizio [Introduzione](getting-started-sample.md) . È tuttavia presente un'operazione aggiuntiva fornita dal contratto di servizio, ovvero `GetCallerIdentity`. Questa operazione restituisce il nome dell'identità del chiamante al chiamante.  

```csharp
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```

 È necessario creare un certificato e assegnarlo utilizzando la Gestione guidata certificati server Web prima di compilare ed eseguire l'esempio. Le definizioni dell'endpoint e dell'associazione nelle impostazioni del file di configurazione abilitano la modalità di sicurezza `TransportWithMessageCredential`, come illustrato nella configurazione di esempio seguente per il client.  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
              address="https://localhost/servicemodelsamples/service.svc"
              binding="wsHttpBinding"
              bindingConfiguration="Binding1"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
        This configuration defines the security mode as TransportWithMessageCredential.  
        and the clientCredentialType as UserName.  
        -->  
      <binding name="Binding1">  
        <security mode ="TransportWithMessageCredential">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 L'indirizzo specificato utilizza lo `https://` schema. La configurazione dell'associazione imposta la modalità di sicurezza su `TransportWithMessageCredential`. La stessa modalità di sicurezza deve essere specificata nel file Web.config del servizio.  
  
 Poiché il certificato utilizzato in questo esempio è un certificato di prova creato con Makecert. exe, viene visualizzato un avviso di sicurezza quando si tenta di accedere a un indirizzo https:, ad esempio `https://localhost/servicemodelsamples/service.svc` , dal browser. Per consentire al client WCF di utilizzare un certificato di prova, è stato aggiunto un altro codice al client per disattivare l'avviso di sicurezza. Il codice e la classe associata non sono richiesti quando si utilizzano i certificati di produzione.  

```csharp
// WARNING: This code is only needed for test certificates such as those created by makecert. It is
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```
  
 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.  
  
```console  
Username authentication required.  
Provide a valid machine or domain account. [domain\\user]  
   Enter username:
YourDomainName\YourAccountName  
   Enter password:
********  
YourDomainName\YourAccountName  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Assicurarsi di aver eseguito le [istruzioni di installazione del certificato Server Internet Information Services (IIS)](iis-server-certificate-installation-instructions.md).  
  
3. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
4. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
