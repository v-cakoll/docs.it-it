---
title: Sicurezza dei messaggi anonima
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: c321cbf9-8c05-4cce-b5a5-4bf7b230ee03
ms.openlocfilehash: 95101b8ec4f5a7fc60d0233ab6685b5c6851b44e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584982"
---
# <a name="message-security-anonymous"></a>Sicurezza dei messaggi anonima
Nell'esempio relativo alla sicurezza dei messaggi anonima viene illustrato come implementare un'applicazione Windows Communication Foundation (WCF) che utilizza la sicurezza a livello di messaggio senza autenticazione client, ma che richiede l'autenticazione del server utilizzando il certificato X. 509 del server. Tutti i messaggi dell'applicazione tra il client e il server vengono firmati e crittografati. Questo esempio è basato sull'esempio [wsHttpBinding](wshttpbinding.md) . Questo esempio è costituito da un programma di console client (.exe) e da una libreria di servizi (.dll) ospitati da Internet Information Services (IIS). Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

 Questo esempio aggiunge una nuova operazione all'interfaccia della calcolatrice che restituisce `True` se il client non viene autenticato.

```csharp
public class CalculatorService : ICalculator
{
    public bool IsCallerAnonymous()
    {
        // ServiceSecurityContext.IsAnonymous returns true if the caller is not authenticated.
        return ServiceSecurityContext.Current.IsAnonymous;
    }
    ...
}
```

 Il servizio espone un solo endpoint per comunicare con il servizio che viene definito mediante un file di configurazione (Web.config). L'endpoint è costituito da un indirizzo, un'associazione e un contratto. L'associazione viene configurata con un'associazione `wsHttpBinding`. La modalità di sicurezza predefinita per l'associazione `wsHttpBinding` è `Message`. L'attributo `clientCredentialType` è impostato su `None`.

```xml
<system.serviceModel>

  <protocolMapping>
    <add scheme="http" binding="wsHttpBinding" />
  </protocolMapping>

  <bindings>
    <wsHttpBinding>
     <!-- This configuration defines the security mode as Message and -->
     <!-- the clientCredentialType as None. This mode provides -->
     <!-- server authentication only using the service certificate. -->

     <binding>
       <security mode="Message">
         <message clientCredentialType="None" />
       </security>
     </binding>
    </wsHttpBinding>
  </bindings>
  ...
</system.serviceModel>
```

 Le credenziali da utilizzare per l'autenticazione del servizio sono specificate in [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) . Il `SubjectName` del certificato server deve contenere lo stesso valore di quello specificato per l'attributo `findValue`, come illustrato nell'esempio di codice seguente.

```xml
<behaviors>
  <serviceBehaviors>
    <behavior>
      <!--
    The serviceCredentials behavior allows you to define a service certificate.
    A service certificate is used by a client to authenticate the service and provide message protection.
    This configuration references the "localhost" certificate installed during the setup instructions.
    -->
      <serviceCredentials>
        <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
      </serviceCredentials>
      <serviceMetadata httpGetEnabled="True"/>
      <serviceDebug includeExceptionDetailInFaults="False" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```

 La configurazione dell'endpoint client è costituita da un indirizzo assoluto per l'endpoint del servizio, l'associazione e il contratto. La modalità di sicurezza del client per l'associazione `wsHttpBinding` è `Message`. L'attributo `clientCredentialType` è impostato su `None`.

```xml
<system.serviceModel>
  <client>
    <endpoint name=""
             address="http://localhost/servicemodelsamples/service.svc"
             binding="wsHttpBinding"
             behaviorConfiguration="ClientCredentialsBehavior"
             bindingConfiguration="Binding1"
             contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </client>

  <bindings>
    <wsHttpBinding>
      <!--This configuration defines the security mode as -->
      <!--Message and the clientCredentialType as None. -->
      <binding name="Binding1">
        <security mode = "Message">
          <message clientCredentialType="None"/>
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>
  ...
</system.serviceModel>
```

 L'esempio imposta <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> su <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust> per l'autenticazione del certificato del servizio. Questa operazione viene eseguita nel file App.config del client, nella sezione `behaviors`. Questo significa che se il certificato si trova nell'archivio Persone attendibili, viene considerato attendibili senza eseguire la convalida della catena di emittenti del certificato. Questa impostazione viene usata nell'esempio per comodità, in modo che possa essere eseguito senza richiedere certificati emessi da un'autorità di certificazione (CA). Questa impostazione è meno protetta dell'impostazione predefinita, ChainTrust. Le implicazioni di sicurezza di questa impostazione devono essere considerate attentamente prima di usare `PeerOrChainTrust` nel codice di produzione.

 L'implementazione client aggiunge una chiamata al `IsCallerAnonymous` metodo e in caso contrario non è diversa dall'esempio [wsHttpBinding](wshttpbinding.md) .

```csharp
// Create a client with a client endpoint configuration.
CalculatorClient client = new CalculatorClient();

// Call the GetCallerIdentity operation.
Console.WriteLine("IsCallerAnonymous returned: {0}", client.IsCallerAnonymous());

// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = client.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

...

//Closing the client gracefully closes the connection and cleans up resources.
client.Close();

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.

```console
IsCallerAnonymous returned: True
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

 Il file batch Setup.bat incluso nell'esempio relativo alla sicurezza dei messaggi anonima consente di configurare il server con un certificato attinente per eseguire un'applicazione ospitata che richiede sicurezza server basata su certificato. Il file batch può essere eseguito in due modalità. Per eseguire il file batch in un solo computer, digitare `setup.bat` nella riga di comando. Per eseguirlo in modalità di servizio, digitare `setup.bat service`. Usare questa modalità quando si esegue l'esempio tra più computer. Per altre informazioni, vedere la procedura di configurazione alla fine di questo argomento.

 Gli elementi seguenti forniscono una breve panoramica delle diverse sezioni dei file batch:

- Creazione del certificato server.

     Le righe seguenti del file batch Setup.bat creano il certificato server da usare.

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

     La variabile %SERVER_NAME% specifica il nome del server. Il certificato viene archiviato nell'archivio LocalMachine. Se il file batch di installazione viene eseguito con un argomento di servizio, ad esempio `setup.bat service`, la variabile %SERVER_NAME% conterrà il nome di dominio completo del computer. In caso contrario, viene usata l'impostazione predefinita localhost.

- Installazione del certificato server nell'archivio certificati attendibili del client.

     La riga seguente copia il certificato server nell'archivio Persone attendibili del client. Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client. Se è già disponibile un certificato impostato come radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il popolamento dell'archivio certificati client con il certificato server non è necessario.

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- Concessione delle autorizzazioni sulla chiave privata del certificato.

     Le righe seguenti del file batch Setup. bat rendono il certificato server archiviato nell'archivio LocalMachine accessibile all'account del processo di lavoro di ASP.NET.

    ```bat
    echo ************
    echo setting privileges on server certificates
    echo ************
    for /F "delims=" %%i in ('"%MSSDK%\bin\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE
    (ver | findstr "5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R
    iisreset
    ```

> [!NOTE]
> Se si usa un'edizione non in lingua inglese di Windows, è necessario modificare il file Setup. bat e sostituire il `NT AUTHORITY\NETWORK SERVICE` nome dell'account con l'equivalente regionale.

### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).

### <a name="to-run-the-sample-on-the-same-computer"></a>Per eseguire l'esempio nello stesso computer

1. Assicurarsi che il percorso includa la cartella in cui sono situati Makecert.exe e FindPrivateKey.exe.

2. Eseguire Setup. bat dalla cartella di installazione dell'esempio in un Prompt dei comandi per gli sviluppatori per l'esecuzione di Visual Studio con privilegi di amministratore. In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.

    > [!NOTE]
    > Il file batch di installazione è progettato per essere eseguito da un Prompt dei comandi per gli sviluppatori per Visual Studio. e richiede che la variabile di ambiente PATH punti alla directory in cui è installato SDK. Questa variabile di ambiente viene impostata automaticamente in un Prompt dei comandi per gli sviluppatori per Visual Studio.  
  
3. Verificare l'accesso al servizio usando un browser immettendo l'indirizzo `http://localhost/servicemodelsamples/service.svc` .  
  
4. Avviare Client.exe da \client\bin. L'attività del client viene visualizzata nella finestra dell'applicazione console.  
  
5. Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-run-the-sample-across-computers"></a>Per eseguire l'esempio tra più computer  
  
1. Creare una directory sul computer del servizio. Creare un'applicazione virtuale denominata servicemodelsamples per questa directory usando lo strumento di gestione di Internet Information Services (IIS).  
  
2. Copiare i file del programma del servizio da \inetpub\wwwroot\servicemodelsamples nella directory virtuale sul computer del servizio. Assicurarsi di copiare i file nella sottodirectory \bin Copiare i file Setup.bat e Cleanup.bat nel computer del servizio.  
  
3. Creare una directory sul client del servizio per i file binari del client.  
  
4. Copiare i file di programma del client nella directory del client sul computer relativo e i file Setup.bat, Cleanup.bat e ImportServiceCert.bat nel client.  
  
5. Sul server, eseguire `setup.bat service` in un prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore. Quando `setup.bat` si esegue con l' `service` argomento viene creato un certificato del servizio con il nome di dominio completo del computer e il certificato del servizio viene esportato in un file denominato Service. cer.  
  
6. Modificare Web. config per riflettere il nuovo nome del certificato (nell' `findValue` attributo in [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ), che corrisponde al nome di dominio completo del computer.  
  
7. Copiare il file Service.cer dalla directory del servizio nella directory del client sul computer relativo.  
  
8. Nel file Client.exe.config presente nel computer client modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio.  
  
9. Sul client, eseguire ImportServiceCert. bat in un Prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore. In questo modo viene importato il certificato del servizio dal file Service.cer nell'archivio CurrentUser - TrustedPeople.  
  
10. Sul computer client avviare Client.exe da un prompt dei comandi. Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-clean-up-after-the-sample"></a>Per eseguire la pulizia dopo l'esempio  
  
- Eseguire Cleanup.bat nella cartella degli esempi dopo che l'esempio è stato completato.  
  
> [!NOTE]
> Questo script non rimuove i certificati del servizio da un client quando si esegue l'esempio tra più computer. Se sono stati eseguiti esempi Windows Communication Foundation (WCF) che usano certificati tra computer, assicurarsi di cancellare i certificati del servizio installati nell'archivio CurrentUser-TrustedPeople. Per eseguire questa operazione, usare il seguente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Ad esempio: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com.`
