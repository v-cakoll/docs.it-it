---
title: Sicurezza dei messaggi nell'accodamento messaggi
ms.date: 03/30/2017
ms.assetid: 329aea9c-fa80-45c0-b2b9-e37fd7b85b38
ms.openlocfilehash: 7d483ff8252469e95dfbddedf31d1506848e1b45
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584922"
---
# <a name="message-security-over-message-queuing"></a>Sicurezza dei messaggi nell'accodamento messaggi
In questo esempio viene illustrato come implementare un'applicazione che utilizza WS-Security con l'autenticazione del certificato X.509v3 per il client e che richiede l'autenticazione del server utilizzando il certificato X.509v3 del server su MSMQ. La sicurezza dei messaggi a volte è più efficace per garantire che i messaggi nell'archivio MSMQ siano crittografati e l'applicazione può eseguire direttamente l'autenticazione del messaggio.

 Questo esempio è basato sull'esempio di [associazione MSMQ transazionale](transacted-msmq-binding.md) . I messaggi vengono crittografati e firmati.

### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Se il servizio viene eseguito prima, verificherà la presenza della coda. Se la coda non è presente, il servizio ne creerà una. È possibile eseguire il servizio prima per creare la coda oppure è possibile crearne una tramite il gestore code MSMQ. Per creare una coda in Windows 2008, eseguire i passaggi riportati di seguito.

    1. Aprire Server Manager in Visual Studio 2012.

    2. Espandere la scheda **funzionalità** .

    3. Fare clic con il pulsante destro del mouse su **code di messaggi private**e selezionare **nuova**, **coda privata**.

    4. Controllare la casella **transazionale** .

    5. Immettere `ServiceModelSamplesTransacted` come nome della nuova coda.

3. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).

### <a name="to-run-the-sample-on-the-same-computer"></a>Per eseguire l'esempio nello stesso computer

1. Assicurarsi che il percorso includa la cartella contenente Makecert.exe e FindPrivateKey.exe.

2. Eseguire Setup.bat dalla cartella di installazione dell'esempio. In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.

    > [!NOTE]
    > Assicurarsi di rimuovere i certificati eseguendo Cleanup.bat una volta completato l'esempio. Negli altri esempi relativi alla sicurezza vengono usati gli stessi certificati.  
  
3. Avviare Service.exe da \service\bin.  
  
4. Avviare Client.exe da \client\bin. L'attività del client viene visualizzata nella finestra dell'applicazione console.  
  
5. Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-run-the-sample-across-computers"></a>Per eseguire l'esempio tra più computer  
  
1. Copiare i file Setup.bat, Cleanup.bat e ImportClientCert.bat nel computer del servizio.  
  
2. Creare una directory sul client del servizio per i file binari del client.  
  
3. Copiare i file di programma del client nella directory del client sul computer relativo e i file Setup.bat, Cleanup.bat e ImportServiceCert.bat nel client.  
  
4. Eseguire `setup.bat service` sul server. Quando `setup.bat` si esegue con l' `service` argomento viene creato un certificato del servizio con il nome di dominio completo del computer e il certificato del servizio viene esportato in un file denominato Service. cer.  
  
5. Modificare Service. exe. config del servizio per riflettere il nuovo nome del certificato (nell' `findValue` attributo in [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ) che corrisponde al nome di dominio completo del computer.  
  
6. Copiare il file Service.cer dalla directory del servizio nella directory del client sul computer relativo.  
  
7. Eseguire `setup.bat client` sul client. Quando si esegue `setup.bat` con l'argomento `client` viene creato un certificato client denominato client.com che viene esportato in un file denominato Client.cer.  
  
8. Nel file Client.exe.config presente nel computer client modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio. Tale operazione viene eseguita sostituendo localhost con il nome di dominio completo del server.  È inoltre necessario modificare il nome di certificato del servizio in modo che corrisponda al nome di dominio completo del computer del servizio (nell'attributo `findValue` dell'elemento `defaultCertificate` di `serviceCertificate` in `clientCredentials`).  
  
9. Copiare il file Client.cer dalla directory del client nella directory del servizio sul server.  
  
10. Eseguire `ImportServiceCert.bat` sul client. In questo modo viene importato il certificato del servizio dal file Service.cer nell'archivio CurrentUser - TrustedPeople.  
  
11. Eseguire `ImportClientCert.bat` sul server. In questo modo il certificato client viene importato dal file Client.cer nell'archivio LocalMachine - TrustedPeople.  
  
12. Sul computer del servizio eseguire Service.exe dal prompt dei comandi.  
  
13. Sul computer client avviare Client.exe dal prompt dei comandi. Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-clean-up-after-the-sample"></a>Per eseguire la pulizia dopo l'esempio  
  
- Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.  
  
    > [!NOTE]
    > Questo script non rimuove i certificati del servizio da un client quando si esegue l'esempio tra più computer. Se sono stati eseguiti esempi Windows Communication Foundation (WCF) che usano certificati tra computer, assicurarsi di cancellare i certificati del servizio installati nell'archivio CurrentUser-TrustedPeople. Per eseguire questa operazione, usare il seguente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Ad esempio: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.

## <a name="requirements"></a>Requisiti
 Questo esempio richiede che MSMQ sia installato e in esecuzione,

## <a name="demonstrates"></a>Dimostra
 Il client crittografa il messaggio con la chiave pubblica del servizio e firma il messaggio utilizzando il relativo certificato. Il servizio che legge il messaggio dalla coda autentica il certificato client con il certificato nell'archivio Persone attendibili. Successivamente decrittografa il messaggio e lo invia all'operazione del servizio.

 Poiché il messaggio di Windows Communication Foundation (WCF) viene portato come payload nel corpo del messaggio MSMQ, il corpo rimane crittografato nell'archivio MSMQ. In questo modo il messaggio viene protetto dalla diffusione indesiderata. Si noti che il servizio MSMQ non è in grado di identificare se il messaggio trasportato è crittografato.

 Nell'esempio viene illustrato come l'autenticazione reciproca al livello del messaggio può essere utilizzata con MSMQ. I certificati vengono scambiati fuori banda. Questo comportamento viene applicato sempre nel caso delle applicazioni accodate poiché non è necessario che il client e il servizio siano in esecuzione contemporaneamente.

## <a name="description"></a>Descrizione
 Il codice del client e del servizio di esempio è uguale all'esempio di [associazione MSMQ transazionale](transacted-msmq-binding.md) con una differenza. Il contratto dell'operazione è annotato con il livello di protezione che suggerisce che il messaggio deve essere firmato e crittografato.

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, ProtectionLevel=ProtectionLevel.EncryptAndSign)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 Per assicurare che il messaggio venga protetto utilizzando il token necessario per identificare il servizio e client, il file App.config contiene informazioni sulle credenziali.

 La configurazione client specifica il certificato del servizio per autenticare il servizio. Tale configurazione utilizza l'archivio del computer locale come archivio attendibile per basarsi sulla validità del servizio. Specifica anche il certificato client allegato al messaggio per l'autenticazione del servizio del client.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>

  <system.serviceModel>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"
                binding="netMsmqBinding"
                bindingConfiguration="messageSecurityBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor"
                behaviorConfiguration="ClientCertificateBehavior" />
    </client>

    <bindings>
        <netMsmqBinding>
            <binding name="messageSecurityBinding">
                <security mode="Message">
                    <message clientCredentialType="Certificate"/>
                </security>
            </binding>
        </netMsmqBinding>
    </bindings>

    <behaviors>
      <endpointBehaviors>
        <behavior name="ClientCertificateBehavior">
          <!--
        The clientCredentials behavior allows one to define a certificate to present to a service.
        A certificate is used by a client to authenticate itself to the service and provide message integrity.
        This configuration references the "client.com" certificate installed during the setup instructions.
        -->
          <clientCredentials>
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />
            <serviceCertificate>
                <defaultCertificate findValue="localhost" storeLocation="CurrentUser" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it is trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
              <authentication certificateValidationMode="PeerOrChainTrust" />
            </serviceCertificate>
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>

  </system.serviceModel>
</configuration>
```

 Si noti che la modalità di sicurezza è impostata su Message e ClientCredentialType è impostato su Certificate.

 La configurazione del servizio include un comportamento del servizio che specifica le credenziali del servizio che vengono utilizzate quando il client autentica il servizio. Il nome del soggetto del certificato server è specificato nell' `findValue` attributo in [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>

  <appSettings>
    <!-- Use appSetting to configure MSMQ queue name. -->
    <add key="queueName" value=".\private$\ServiceModelSamplesMessageSecurity" />
  </appSettings>

  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.OrderProcessorService"
          behaviorConfiguration="PurchaseOrderServiceBehavior">
        <host>
          <baseAddresses>
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
          </baseAddresses>
        </host>
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"
                  binding="netMsmqBinding"
                  bindingConfiguration="messageSecurityBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
        <!-- The mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex. -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>

    <bindings>
        <netMsmqBinding>
            <binding name="messageSecurityBinding">
                <security mode="Message">
                    <message clientCredentialType="Certificate" />
                </security>
            </binding>
        </netMsmqBinding>
    </bindings>

    <behaviors>
      <serviceBehaviors>
        <behavior name="PurchaseOrderServiceBehavior">
          <serviceMetadata httpGetEnabled="True"/>
          <!--
               The serviceCredentials behavior allows one to define a service certificate.
               A service certificate is used by the service to authenticate itself to its clients and to provide message protection.
               This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCredentials>
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
            <clientCertificate>
                <certificate findValue="client.com" storeLocation="LocalMachine" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it is trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
              <authentication certificateValidationMode="PeerOrChainTrust" />
            </clientCertificate>
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>

</configuration>
```

 Nell'esempio viene illustrato il controllo dell'autenticazione mediante la configurazione e come ottenere l'identità del chiamante dal contesto di sicurezza, come illustrato nel codice di esempio seguente:

```csharp
// Service class which implements the service contract.
// Added code to write output to the console window.
public class OrderProcessorService : IOrderProcessor
{
    private string GetCallerIdentity()
    {
        // The client certificate is not mapped to a Windows identity by default.
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information
        // in the certificate that the client used to authenticate itself to the service.
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Console.WriteLine("Client's Identity {0} ", GetCallerIdentity());
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
    }
  //…
}
```

 Quando viene eseguito, il codice del servizio visualizza l'identificazione client. Di seguito è riportato l'output di esempio del codice del servizio:

```console
The service is ready.
Press <ENTER> to terminate service.

Client's Identity CN=client.com; ECA6629A3C695D01832D77EEE836E04891DE9D3C
Processing Purchase Order: 6536e097-da96-4773-9da3-77bab4345b5d
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

## <a name="comments"></a>Commenti

- Creazione del certificato del client.

     La riga seguente nel file batch crea il certificato client. Il nome client specificato viene utilizzato nel nome del soggetto del certificato creato. Il certificato viene inserito nell'archivio `My` nel percorso `CurrentUser`.

    ```bat
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

- Installazione del certificato client nell'archivio certificati attendibili del server.

     La riga seguente nel file batch copia il certificato client nell'archivio TrustedPeople del server in modo che il server possa prendere le decisioni pertinenti in tema di attendibilità. Affinché un certificato installato nell'archivio TrustedPeople sia considerato attendibile da un servizio Windows Communication Foundation (WCF), è necessario che la modalità di convalida del certificato client sia impostata sul `PeerOrChainTrust` `PeerTrust` valore o. Per informazioni sull'esecuzione di questa operazione mediante un file di configurazione, vedere l'esempio di configurazione del servizio precedente.

    ```bat
    echo ************
    echo copying client cert to server's LocalMachine store
    echo ************
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

- Creazione del certificato server.

     Le righe seguenti del file batch Setup.bat creano il certificato server da utilizzare:

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

     La variabile %SERVER_NAME% specifica il nome del server. Il certificato viene archiviato nell'archivio LocalMachine. Se il file batch di installazione viene eseguito con un argomento di servizio (ad esempio, `setup.bat service` ),% server_name% contiene il nome di dominio completo del computer. In caso contrario, il valore predefinito è localhost

- Installazione del certificato server nell'archivio certificati attendibili del client

     La riga seguente copia il certificato server nell'archivio Persone attendibili del client. Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client. Se è già disponibile un certificato impostato come radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il popolamento dell'archivio certificati client con il certificato server non è necessario.

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

    > [!NOTE]
    > Se si usa un'edizione non in lingua inglese di Microsoft Windows, è necessario modificare il file Setup. bat e sostituire il nome dell'account "NT AUTHORITY\NETWORK SERVICE" con l'equivalente regionale.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\MessageSecurity`  
