---
title: 'Procedura: specificare credenziali di sicurezza del canale'
ms.date: 03/30/2017
ms.assetid: f8e03f47-9c4f-4dd5-8f85-429e6d876119
ms.openlocfilehash: 72fdcd18fba2eabe8255f73acd240e12e57d56ea
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144708"
---
# <a name="how-to-specify-channel-security-credentials"></a>Procedura: specificare credenziali di sicurezza del canale
Il moniker del servizio Windows Communication Foundation (WCF) consente alle applicazioni COM di chiamare i servizi WCF. Per la maggior parte dei servizi WCF è necessario che il client specifichi le credenziali per l'autenticazione e l'autorizzazione. Quando si chiama un servizio WCF da un client WCF, è possibile specificare queste credenziali nel codice gestito o in un file di configurazione dell'applicazione. Quando si chiama un servizio WCF da un'applicazione COM, è possibile usare l' <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interfaccia per specificare le credenziali. In questo argomento vengono illustrate varie modalità di specifica delle credenziali mediante l'interfaccia <xref:System.ServiceModel.ComIntegration.IChannelCredentials>.  
  
> [!NOTE]
> <xref:System.ServiceModel.ComIntegration.IChannelCredentials> è un'interfaccia basata su IDispatch nella quale non viene visualizzata la funzionalità IntelliSense nell'ambiente Visual Studio.  
  
 In questo articolo verrà utilizzato il servizio WCF definito nell' [esempio relativo alla sicurezza dei messaggi](../../../../docs/framework/wcf/samples/message-security-sample.md).  
  
### <a name="to-specify-a-client-certificate"></a>Per specificare un certificato client  
  
1. Eseguire il file Setup.bat nella directory della protezione messaggi per creare e installare i certificati di prova obbligatori.  
  
2. Aprire il progetto Message Security.  
  
3. Aggiungere `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` alla `ICalculator` definizione dell'interfaccia.  
  
4. Aggiungere `bindingNamespace="http://Microsoft.ServiceModel.Samples"` al tag dell'endpoint nel file app. config per il servizio.  
  
5. Compilare l'esempio di sicurezza dei messaggi ed eseguire Service.exe. Utilizzare Internet Explorer e passare all'URI del servizio ( `http://localhost:8000/ServiceModelSamples/Service` ) per assicurarsi che il servizio sia funzionante.  
  
6. Aprire Visual Basic 6.0 e creare un nuovo file standard con estensione exe. Aggiungere un pulsante al form e fare doppio clic su di esso per aggiungere il codice seguente al gestore Click:  
  
    ```vb  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
        monString = monString + ", binding=BasicHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
        Set monikerProxy = GetObject(monString)  
  
        'Set the Service Certificate.  
     monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetDefaultServiceCertificateFromStore "CurrentUser", "TrustedPeople", "FindBySubjectName", "localhost"  
  
        'Set the Client Certificate.  
        monikerProxy.ChannelCredentials.SetClientCertificateFromStoreByName "CN=client.com", "CurrentUser", "My"  
        MsgBox monikerProxy.Add(3, 4)  
    ```  
  
7. Eseguire l'applicazione Visual Basic e verificare i risultati.  
  
     Nell'applicazione Visual Basic verrà visualizzata una finestra di messaggio con il risultato relativo alla chiamata di Add(3, 4). Per impostare il certificato client è inoltre possibile usare <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> o <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> al posto di <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29>:  
  
    ```vb  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
> Perché questa chiamata venga eseguita correttamente, il certificato client deve essere considerato attendibile nel computer in cui è in esecuzione il client.  
  
> [!NOTE]
> Se il formato del moniker non è valido o se il servizio non è disponibile, la chiamata a `GetObject` restituirà un errore di sintassi non valida. Se si riceve questo errore, verificare che il moniker che si sta usando sia valido e che il servizio sia disponibile.  
  
### <a name="to-specify-user-name-and-password"></a>Per specificare un nome utente e una password  
  
1. Modificare il file Service App.config per usare `wsHttpBinding`. Questa operazione è necessaria per la convalida del nome utente e della password.  

2. Impostare `clientCredentialType` su UserName:  

3. Aprire Visual Basic 6.0 e creare un nuovo file standard con estensione exe. Aggiungere un pulsante al form e fare doppio clic su di esso per aggiungere il codice seguente al gestore Click:  
  
    ```vb
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set monikerProxy = GetObject(monString)  
  
    monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetUserNameCredential "username", "password"  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
4. Eseguire l'applicazione Visual Basic e verificare i risultati. Nell'applicazione Visual Basic verrà visualizzata una finestra di messaggio con il risultato relativo alla chiamata di Add(3, 4).  
  
    > [!NOTE]
    > L'associazione specificata nel moniker del servizio in questo esempio è stata impostata su WSHttpBinding_ICalculator. Nella chiamata a <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29> è inoltre necessario fornire un nome utente e una password validi.  
  
### <a name="to-specify-windows-credentials"></a>Per specificare credenziali di Windows.  
  
1. Impostare `clientCredentialType` su Windows nel file App.config del servizio:  

2. Aprire Visual Basic 6.0 e creare un nuovo file standard con estensione exe. Aggiungere un pulsante al form e fare doppio clic su di esso per aggiungere il codice seguente al gestore Click:  
  
    ```vb
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", upnidentity=domain\userID"  
  
    Set monikerProxy = GetObject(monString)  
     monikerProxy.ChannelCredentials.SetWindowsCredential "domain", "userID", "password", 1, True  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
3. Eseguire l'applicazione Visual Basic e verificare i risultati. Nell'applicazione Visual Basic verrà visualizzata una finestra di messaggio con il risultato relativo alla chiamata di Add(3, 4).  
  
    > [!NOTE]
    > È necessario sostituire "dominio", "IDUtente" e "password" con valori validi.  
  
### <a name="to-specify-an-issue-token"></a>Per specificare un token di pubblicazione  
  
1. I token di pubblicazione vengono usati soltanto per applicazioni che usano la protezione federata. Per altre informazioni sulla sicurezza federata, vedere [Federazione e token emessi](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) ed [esempio di Federazione](../../../../docs/framework/wcf/samples/federation-sample.md).  
  
     L'esempio di codice Visual Basic seguente mostra come chiamare il metodo <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>:  
  
    ```vb
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     Per altre informazioni sui parametri relativi a questo metodo, vedere <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.  
  
## <a name="see-also"></a>Vedi anche

- [Federazione](../../../../docs/framework/wcf/feature-details/federation.md)
- [Procedura: configurare le credenziali in un servizio federativo](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Procedura: creare un client federato](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [Sicurezza dei messaggi](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)
- [Associazioni e protezione](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
