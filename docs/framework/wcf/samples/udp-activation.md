---
title: Attivazione UDP
ms.date: 03/30/2017
ms.assetid: 4b0ccd10-0dfb-4603-93f9-f0857c581cb7
ms.openlocfilehash: 13d20524693b234a14b2b31061c6259f75b1c0b8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591108"
---
# <a name="udp-activation"></a>Attivazione UDP
Questo esempio è basato sull'esempio [Transport: UDP](transport-udp.md) . Estende l'esempio [Transport: UDP](transport-udp.md) per supportare l'attivazione del processo mediante il servizio di attivazione dei processi di Windows (was).  
  
 L'esempio è costituito da tre parti principali:  
  
- Un attivatore del protocollo UDP, un processo autonomo che riceve messaggi UDP per conto delle applicazioni che devono essere attivate.  
  
- Un client che utilizza il trasporto personalizzato UDP per inviare messaggi.  
  
- Un servizio (ospitato in un processo di lavoro attivato da WAS) che riceve messaggi sul trasporto personalizzato UDP.  
  
## <a name="udp-protocol-activator"></a>Attivatore del protocollo UDP  
 L'attivatore del protocollo UDP è un bridge tra il client WCF e il servizio WCF. Fornisce la comunicazione dati tramite il protocollo UDP a livello di trasporto. e ha due funzioni principali:  
  
- Adattatore listener (LA) WAS, che collabora con WAS per attivare processi in risposta ai messaggi in arrivo.  
  
- Listener protocollo UDP, che accetta messaggi UDP per conto delle applicazioni che devono essere attivate.  
  
 L'attivatore deve essere in esecuzione come programma autonomo sul server. In genere, gli adattatori listener (ad esempio NetTcpActivator e NetPipeActivator) vengono implementati nei servizi Windows di lunga durata. Tuttavia, per maggiore semplicità e chiarezza, questo esempio implementa l'attivatore del protocollo come applicazione autonoma.  
  
### <a name="was-listener-adapter"></a>Adattatore listener WAS  
 L'adattatore listener WAS per UDP è implementato nella classe `UdpListenerAdapter`. È il modulo che interagisce con WAS per eseguire l'attivazione dell'applicazione per il protocollo UDP. Questo risultato viene ottenuto chiamando le seguenti API Webhost:  
  
- `WebhostRegisterProtocol`  
  
- `WebhostUnregisterProtocol`  
  
- `WebhostOpenListenerChannelInstance`  
  
- `WebhostCloseAllListenerChannelInstances`  
  
 Dopo la chiamata iniziale a `WebhostRegisterProtocol`, l'adattatore del listener riceve l'elemento `ApplicationCreated` callback da WAS per tutte le applicazioni registrate in applicationHost.config (in %windir%\system32\inetsrv). In questo esempio, vengono gestite solo le applicazioni con il protocollo UDP (con l'ID del protocollo "net.udp") abilitato. Altre implementazioni possono gestire questo contesto in modo diverso se tali implementazioni rispondono alle modifiche dinamiche di configurazione all'applicazione (ad esempio, una transizione dell'applicazione da disabilitata ad abilitata).  
  
 Quando si riceve l'elemento `ConfigManagerInitializationCompleted` di callback, ciò indica che WAS ha completato tutte le notifiche per l'inizializzazione del protocollo. A questo punto, l'adattatore del listener è pronto per elaborare le richieste di attivazione.  
  
 Quando una nuova richiesta viene ricevuta per la prima volta per un'applicazione, l'adattatore del listener chiama `WebhostOpenListenerChannelInstance` in WAS per avviare il processo di lavoro, se non è ancora stato avviato. I gestori del protocollo vengono quindi caricati e la comunicazione tra l'adattatore del listener e l'applicazione virtuale può avere inizio.  
  
 L'adapter listener viene registrato in%SystemRoot%\System32\inetsrv\ApplicationHost.config nella `listenerAdapters` sezione < > come segue:  
  
```xml  
<add name="net.udp" identity="S-1-5-21-2127521184-1604012920-1887927527-387045" />  
```  
  
### <a name="protocol-listener"></a>Listener del protocollo  
 Il listener del protocollo UDP è un modulo all'interno dell'attivatore del protocollo che è in ascolto su un endpoint UDP per conto dell'applicazione virtuale, ed è implementato nella classe `UdpSocketListener`. L'endpoint è rappresentato come `IPEndpoint` per il quale viene estratto il numero della porta dall'associazione del protocollo per il sito.  
  
### <a name="control-service"></a>Servizio di controllo  
 In questo esempio viene usato WCF per comunicare tra l'attivatore e il processo di lavoro WAS. Il servizio che si trova risiede nell'attivatore è definito servizio di controllo.  
  
## <a name="protocol-handlers"></a>Gestori del protocollo  
 Quando l'adattatore del listener chiama `WebhostOpenListenerChannelInstance`, la gestione processi WAS avvia il processo di lavoro, se non è stato avviato. La gestione applicazioni nel processo di lavoro carica quindi il gestore del protocollo del processo (PPH, Process Protocol Handler) di UDP con la richiesta per tale `ListenerChannelId`. Il gestore delle chiamate in ha a sua volta chiamate `IAdphManager` .`StartAppDomainProtocolListenerChannel` per avviare il gestore del protocollo AppDomain UDP (ADPH).  
  
## <a name="hostedudptransportconfiguration"></a>HostedUDPTransportConfiguration  
 Le informazioni vengono registrate in Web.config come segue:  
  
```xml  
<serviceHostingEnvironment>  
<add name="net.udp" transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />  
</serviceHostingEnvironment>  
```  
  
## <a name="special-setup-for-this-sample"></a>Installazione speciale per questo esempio  
 Questo esempio può essere compilato ed eseguito solo in Windows Vista, Windows Server 2008 o Windows 7. Per eseguire l'esempio, impostare prima tutti i componenti correttamente. Utilizzare i passaggi seguenti per installare l'esempio.  
  
#### <a name="to-set-up-this-sample"></a>Per impostare questo esempio  
  
1. Installare ASP.NET 4,0 usando il comando seguente.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Compilare il progetto su Windows Vista. Dopo la compilazione, vengono eseguite anche le operazioni seguenti nella fase post-compilazione:  
  
    - Installa l'associazione UDP al sito "Sito Web predefinito".  
  
    - Crea l'applicazione virtuale "ServiceModelSamples" per puntare al percorso fisico: "%SystemDrive%\inetpub\wwwroot\servicemodelsamples".  
  
    - Abilita anche il protocollo "net.udp" per questa applicazione virtuale.  
  
3. Avviare l'applicazione dell'interfaccia utente "WasNetActivator.exe". Fare clic sulla scheda **installazione** , selezionare le caselle di controllo seguenti e quindi fare clic su **Installa** per installarle:  
  
    - Adattatore listener UDP  
  
    - Gestori del protocollo UDP  
  
4. Fare clic sulla scheda **attivazione** dell'applicazione dell'interfaccia utente "WasNetActivator. exe". Fare clic sul pulsante **Start** per avviare l'adapter listener. È ora possibile eseguire il programma.  
  
    > [!NOTE]
    > Dopo aver concluso l'esempio, è necessario eseguire Cleanup.bat per rimuovere l'associazione net.udp dal "Sito Web predefinito".  
  
## <a name="sample-usage"></a>Esempio di utilizzo  
 Dopo la compilazione, vengono generati quattro file binari diversi:  
  
- Client.exe: il codice del client. Il file App.config viene compilato nel file di configurazione del client Client.exe.config.  
  
- UDPActivation.dll: la libreria che contiene tutte le principali implementazioni UDP.  
  
- Service.dll: il codice del servizio. Questo file viene copiato nella directory \bin dell'applicazione virtuale ServiceModelSamples. Il file del servizio è Service. svc e il file di configurazione è Web. config. Dopo la compilazione, vengono copiati nel percorso seguente:%SystemDrive%\Inetpub\wwwroot\ServiceModelSamples.  
  
- WasNetActivator: il programma attivatore di UDP.  
  
- Verificare che tutte le parti necessarie siano installate correttamente. Nei passaggi seguenti viene illustrato come eseguire l'esempio:  
  
1. Verificare che i servizi Windows seguenti siano stati avviati:  
  
    - Servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service).  
  
    - Internet Information Services (IIS): W3SVC.  
  
2. Quindi avviare l'attivatore, WasNetActivator.exe. Nella scheda **attivazione** , l'unico protocollo **UDP**è selezionato nell'elenco a discesa. Fare clic sul pulsante **Start** per avviare l'attivatore.  
  
3. Quando l'attivatore è stato avviato, è possibile eseguire il codice client eseguendo Client.exe da una finestra di comando. Di seguito è riportato un output di esempio:  
  
    ```console  
    Testing Udp Activation.  
    Start the status service.  
    Sending UDP datagrams.  
    Type a word that you want to say to the server: Hello, world!  
        Sending datagram: Hello, world![0]  
        Sending datagram: Hello, world![1]  
        Sending datagram: Hello, world![2]  
        Sending datagram: Hello, world![3]  
        Sending datagram: Hello, world![4]  
    Calling UDP duplex contract (ICalculatorContract).  
        0 + 0 = 0  
        1 + 2 = 3  
        2 + 4 = 6  
        3 + 6 = 9  
        4 + 8 = 12  
    Getting status and dump server traces:  
        Operation 'Hello' is called: Hello, world![0]  
        Operation 'Hello' is called: Hello, world![1]  
        Operation 'Hello' is called: Hello, world![2]  
        Operation 'Hello' is called: Hello, world![3]  
        Operation 'Hello' is called: Hello, world![4]  
        Operation 'Add' is called: 0 + 0  
        Operation 'Add' is called: 1 + 2  
        Operation 'Add' is called: 2 + 4  
        Operation 'Add' is called: 3 + 6  
        Operation 'Add' is called: 4 + 8  
    Press <ENTER> to complete test.  
    ```  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\UdpActivation`  
