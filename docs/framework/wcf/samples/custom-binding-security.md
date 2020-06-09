---
title: Sicurezza delle associazioni personalizzate
ms.date: 03/30/2017
ms.assetid: a6383dff-4308-46d2-bc6d-acd4e18b4b8d
ms.openlocfilehash: eb575594cec9ea714578bc104344acc14b00e9df
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592463"
---
# <a name="custom-binding-security"></a>Sicurezza delle associazioni personalizzate

In questo esempio viene illustrato come configurare la sicurezza mediante un'associazione personalizzata. Viene mostrato come usare un'associazione personalizzata per abilitare la sicurezza a livello di messaggio insieme con un trasporto sicuro. Questo è utile quando è necessario un trasporto protetto per trasmettere i messaggi tra client e servizio e simultaneamente i messaggi devono essere protetti a livello di messaggio. Questa configurazione non è supportata dalle associazioni fornite dal sistema.

Questo esempio è costituito da un programma di console client (EXE) e un programma di console del servizio (EXE). Il servizio implementa un contratto duplex. Il contratto è definito dall'interfaccia `ICalculatorDuplex`, che espone operazioni matematiche (somma, sottrazione, moltiplicazione e divisione). L'interfaccia `ICalculatorDuplex` consente al client di eseguire operazioni matematiche, calcolando un risultato in una sessione. Il servizio potrebbe restituire risultati sull'interfaccia `ICalculatorDuplexCallback` indipendentemente. Poiché occorre definire un contesto per correlare il set di messaggi scambiati fra il client e il servizio, i contratti duplex richiedono una sessione. Viene definita un'associazione personalizzata che supporta la comunicazione duplex ed è protetta.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

La configurazione del servizio definisce un'associazione personalizzata che supporta i seguenti elementi:

- Comunicazione TCP protetta tramite il protocollo TLS/SSL

- Sicurezza dei messaggi di Windows

La configurazione dell'associazione personalizzata consente il trasporto protetto abilitando simultaneamente la sicurezza a livello di messaggio. L'ordinamento degli elementi di associazione è importante per la definizione di un'associazione personalizzata, perché ogni rappresenta un livello nello stack dei canali (vedere [binding personalizzati](../extending/custom-bindings.md)). L'associazione personalizzata viene definita nei file di configurazione del servizio e del client, come illustrato nell'esempio di configurazione seguente.

```xml
<bindings>
  <!-- Configure a custom binding. -->
  <customBinding>
    <binding name="Binding1">
      <security authenticationMode="SecureConversation"
                 requireSecurityContextCancellation="true">
      </security>
      <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>
      <sslStreamSecurity requireClientCertificate="false"/>
      <tcpTransport/>
    </binding>
  </customBinding>
</bindings>
```

L'associazione personalizzata usa un certificato del servizio per autenticare il servizio sul livello del trasporto e proteggere i messaggi durante la trasmissione tra client e servizio. Ciò viene ottenuto dall'elemento di associazione `sslStreamSecurity`. Il certificato del servizio viene configurato utilizzando un comportamento del servizio come illustrato nell'esempio di configurazione seguente.

```xml
<behaviors>
    <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
        <serviceMetadata />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <serviceCredentials>
        <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName"/>
        </serviceCredentials>
    </behavior>
    </serviceBehaviors>
</behaviors>
```

L'associazione personalizzata usa inoltre la sicurezza dei messaggi con tipo di credenziale di Windows, che è il tipo di credenziale predefinito. Ciò viene ottenuto dall'elemento di associazione `security`. Sia il client che il servizio vengono autenticati mediante la sicurezza a livello di messaggio se è disponibile l'autenticazione Kerberos. Questa situazione si verifica se l'esempio viene eseguito nell'ambiente di Active Directory. Se il meccanismo di autenticazione Kerberos non è disponibile, viene usata l'autenticazione NTLM. Tale autenticazione viene eseguita tra il client e il servizio, ma non tra il servizio e il client. L' `security` elemento di associazione è configurato per l'utilizzo di `SecureConversation` `authenticationType` , che comporta la creazione di una sessione di sicurezza nel client e nel servizio. Questa operazione è necessaria per consentire il funzionamento del contratto duplex del servizio.

Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.

```console
Press <ENTER> to terminate client.
Result(100)
Result(50)
Result(882.5)
Result(441.25)
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)
```

Quando si esegue l'esempio, vengono visualizzati i messaggi restituiti al client sull'interfaccia di callback inviata dal servizio. Una volta completate tutte le operazioni, vengono visualizzati tutti i risultati intermedi, seguiti dall'intera equazione. Premere INVIO per arrestare il client.

Il file batch Setup.bat incluso consente di configurare il client e il server con il certificato del servizio attinente per eseguire un'applicazione ospitata che richiede sicurezza basata su certificato. Questo file batch deve essere modificato per funzionare tra computer diversi o nel caso in cui non sia ospitato.

Di seguito viene fornita una breve panoramica delle varie sezioni dei file batch che si applicano a questo esempio, in modo che possano essere modificate per l'esecuzione nella configurazione appropriata:

- Creazione del certificato server.

  Le righe seguenti del file Setup.bat creano il certificato server da utilizzare. La variabile `%SERVER_NAME%` specifica il nome del server. Modificare questa variabile per specificare nome del server. Questo file batch imposta localhost come valore predefinito del nome del server.

  Il certificato viene archiviato in CurrentUser per i servizi ospitati su Web.

  ```bat
  echo ************
  echo Server cert setup starting
  echo %SERVER_NAME%
  echo ************
  echo making server cert
  echo ************
  makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
  ```

- Installazione del certificato server nell'archivio certificati attendibili del client.

  Le righe seguenti nel file Setup.bat copiano il certificato server nell'archivio Persone attendibili del client. Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client. Se è già disponibile un certificato impostato come radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il popolamento dell'archivio certificati client con il certificato server non è necessario.

  ```console
  certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
  ```

  > [!NOTE]
  > Il file batch Setup.bat è progettato per essere eseguito da un prompt dei comandi di Visual Studio 2010 e richiede che la variabile di ambiente MSSDK punti alla directory in cui è installato SDK. Questa variabile di ambiente viene impostata automaticamente in un prompt dei comandi di Visual Studio 2010.

### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).

3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).

### <a name="to-run-the-sample-on-the-same-computer"></a>Per eseguire l'esempio nello stesso computer

1. Aprire una finestra di Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi di amministratore ed eseguire Setup. bat dalla cartella di installazione dell'esempio. In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.

    > [!NOTE]
    > Il file batch Setup. bat è progettato per essere eseguito da un prompt dei comandi di Visual Studio 2012. La variabile di ambiente PATH impostata nel prompt dei comandi di Visual Studio 2012 punta alla directory che contiene i file eseguibili richiesti dallo script Setup. bat.

2. Avviare Service.exe da \service\bin.

3. Avviare Client.exe da \client\bin. L'attività del client viene visualizzata nella finestra dell'applicazione console.

4. Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).

### <a name="to-run-the-sample-across-computers"></a>Per eseguire l'esempio tra più computer

1. Sul computer del servizio:

    1. Creare una directory virtuale denominata ServiceModelSamples sul computer del servizio.

    2. Copiare i file del programma del servizio da \inetpub\wwwroot\servicemodelsamples nella directory virtuale sul computer del servizio. Assicurarsi di copiare i file nella sottodirectory \bin

    3. Copiare i file Setup.bat e Cleanup.bat nel computer del servizio.

    4. Eseguire il comando seguente in un Prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore: `Setup.bat service` . In questo modo verrà creato il certificato del servizio con il nome dell'oggetto che corrisponde al nome del computer in cui viene eseguito il file batch.

        > [!NOTE]
        > Il file batch Setup.bat è progettato per essere eseguito da un prompt dei comandi di Visual Studio 2010 e richiede che la variabile di ambiente PATH punti alla directory in cui è installato SDK. Questa variabile di ambiente viene impostata automaticamente in un prompt dei comandi di Visual Studio 2010.

    5. Modificare all' [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) interno del file Service. exe. config in modo che corrisponda al nome del soggetto del certificato generato nel passaggio precedente.

    6. Eseguire Service.exe da un prompt dei comandi.

2. Nel computer client:

    1. Copiare i file del programma client dalla cartella \client\bin\ sul computer client. Copiare inoltre il file Cleanup.bat.

    2. Eseguire Cleanup.bat per rimuovere i certificati obsoleti dagli esempi precedenti.

    3. Esportare il certificato del servizio aprendo un Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi amministrativi ed eseguendo il comando seguente sul computer del servizio (sostituire `%SERVER_NAME%` con il nome completo del computer in cui è in esecuzione il servizio):

        ```console
        certmgr -put -r LocalMachine -s My -c -n %SERVER_NAME% %SERVER_NAME%.cer
        ```

    4. Copiare %NOME_SERVER%.cer sul computer client (sostituire %NOME_SERVER% con il nome completo del computer in cui viene eseguito il servizio).

    5. Importare il certificato del servizio aprendo un Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi amministrativi ed eseguendo il comando seguente nel computer client (sostituire% SERVER_NAME% con il nome completo del computer in cui è in esecuzione il servizio):

        ```console
        certmgr.exe -add -c %SERVER_NAME%.cer -s -r CurrentUser TrustedPeople
        ```

        I passaggi c, d ed e non sono necessari se il certificato viene emesso da un'autorità emittente attendibile.

    6. Modificare il file App.config del client come indicato di seguito:

        ```xml
        <client>
            <endpoint name="default"
                address="net.tcp://ReplaceThisWithServiceMachineName:8000/ServiceModelSamples/Service"
                binding="customBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex"
                behaviorConfiguration="CalculatorClientBehavior" />
        </client>
        ```

    7. Se il servizio viene eseguito in un account diverso da NetworkService o LocalSystem in un ambiente del dominio, potrebbe essere necessario modificare l'identità dell'endpoint del servizio nel file App.config del client per impostare il nome UPN o SPN appropriato basato sull'account utilizzato per eseguire il servizio. Per ulteriori informazioni sull'identità dell'endpoint, vedere l'argomento relativo a [identità e autenticazione del servizio](../feature-details/service-identity-and-authentication.md) .

    8. Eseguire Client.exe da un prompt dei comandi.

### <a name="to-clean-up-after-the-sample"></a>Per eseguire la pulizia dopo l'esempio

- Eseguire Cleanup.bat nella cartella degli esempi dopo che l'esempio è stato completato.
