---
title: Risolvere i problemi di Get avviato con le esercitazioni di Windows Communication Foundation
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 8089e0fee262d07be591069982b1aacfbeae2521
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791469"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>Risolvere i problemi di Get avviato con le esercitazioni di Windows Communication Foundation

Questo articolo fornisce soluzioni per gli errori che possono verificarsi quando si seguono i passaggi descritti in e i problemi più comuni di [esercitazione: Iniziare con le applicazioni di Windows Communication Foundation](getting-started-tutorial.md). 
  
## <a name="common-problems"></a>Problemi comuni

**Non riesco a trovare i file di progetto sul disco rigido.**

 Visual Studio salva i file di progetto in *C:\Users\\&lt;nome utente&gt;\source\repos*.  

**Non è possibile trovare il *app. config* generati da file *Svcutil.exe*.**

 In Visual Studio, il **Aggiungi elemento esistente** finestra Visualizza solo i file con le estensioni seguenti per impostazione predefinita: 
- *.cs* 
- *.resx* 
- *.settings*
- *.xsd* 
- *.wsdl*

Per visualizzare tutti i tipi di file, selezionare **tutti i file (\*.\*)**  nell'elenco nell'angolo in basso a destra dell'elenco a discesa la **Aggiungi elemento esistente** finestra.  
  
## <a name="common-errors"></a>Errori comuni

### <a name="compile-the-service-application"></a>Compilare l'applicazione di servizio 

**Errore BC30420 'Sub Main' non è stato trovato in 'GettingStartedHost.Module1'.**

Il punto di ingresso non è corretto per l'applicazione Visual Basic. Apportare le modifiche seguenti:

   1. Nel **Esplora soluzioni** finestra, seleziona la **GettingStartedHost** cartella e quindi selezionare **proprietà** dal menu di scelta rapida.
    a. Nel **GettingStartedHost** finestra, per **oggetto di avvio**, selezionare **Service.Program** (o il punto di ingresso per un'applicazione specifica) dall'elenco. 
    b. Dal menu principale, selezionare **File** > **Salva tutto**.

### <a name="run-the-service-application"></a>Eseguire l'applicazione di servizio 

**HTTP non è stato possibile registrare l'URL ' http:\// +: 8000/GettingStarted/CalculatorService '. Il processo non dispone dei diritti di accesso a questo spazio dei nomi.** 

 Per l'accesso appropriato, avviare il processo che ospita il servizio Windows Communication Foundation (WCF) con privilegi amministrativi:
- Per Visual Studio: Selezionare il programma Visual Studio nel **avviare** dal menu e quindi selezionare **ulteriori** > **Esegui come amministratore** dal menu di scelta rapida.
- Per una finestra della console: Selezionare **prompt dei comandi** nel **avviare** dal menu e quindi selezionare **altre** > **Esegui come amministratore** dal collegamento menu di scelta.
- Per Windows Explorer: Selezionare il file eseguibile e quindi selezionare **Esegui come amministratore** dal menu di scelta rapida.

### <a name="compile-the-client-application"></a>Compilare l'applicazione client

**'CalculatorClient', non contiene una definizione per '\<nome del metodo >' e alcun metodo di estensione '\<nome metodo >' che accetta un primo argomento di tipo 'CalculatorClient' è stato possibile trovare (probabilmente manca un usando direttiva o un riferimento all'assembly?)**  

Solo i metodi che si contrassegno con la `ServiceOperationAttribute` attributo vengono esposte pubblicamente. Se si omette il `ServiceOperationAttribute` attributo da un metodo nel `ICalculator` interfaccia, viene visualizzato questo messaggio di errore durante la compilazione.  

**Il nome di tipo o spazio dei nomi 'CalculatorClient' non è stato trovato (probabilmente manca un utilizzo della direttiva o un riferimento all'assembly?)**

 Questo errore viene visualizzato se non si aggiunge il *generatedProxy.cs* (o *generatedProxy.vb*) al progetto client quando è stato generato con il *Svcutil.exe* strumento .  

### <a name="run-the-client-application"></a>Eseguire l'applicazione client

**Eccezione non gestita: System.ServiceModel.EndpointNotFoundException: Non è riuscito a connettersi a ' http:\//localhost:8000/GettingStarted/CalculatorService '. Codice di errore TCP 10061: È stato possibile stabilire la connessione rifiuto persistente del computer di destinazione.**

Questo errore si verifica se si esegue l'applicazione client senza prima avviare il servizio. In primo luogo, eseguire l'applicazione host per avviare il servizio e quindi eseguire l'applicazione client.

### <a name="use-the-svcutilexe-tool"></a>Usare lo strumento Svcutil.exe
   
**'Svcutil' non è riconosciuto come comando interno o esterno, programma eseguibile o file batch.**

 *Svcutil.exe* deve trovarsi nel percorso di sistema. La soluzione più semplice consiste nell'utilizzare il prompt dei comandi di Visual Studio. Dal **avviare** menu, seleziona il **Visual Studio \<versione >** directory, quindi selezionare **prompt dei comandi per gli sviluppatori per VS \<versione >**. Questo prompt dei comandi imposta il percorso di sistema per i percorsi corretti per tutti gli strumenti forniti come parte di Visual Studio.  
  
### <a name="run-the-service-and-client-applications"></a>Eseguire le applicazioni di servizio e client

**System.ServiceModel.Security.SecurityNegotiationException: Negoziazione di sicurezza SOAP con ' http:\//localhost:8000/GettingStarted/CalculatorService ' per la destinazione ' http:\//localhost:8000/GettingStarted/CalculatorService ' non è riuscita**  

Questo errore si verifica in un computer aggiunto al dominio che non ha connettività di rete. Connettere il computer alla rete o disattivare la sicurezza per il servizio sia nel client. 

Per disattivare la sicurezza:

- Per il servizio, sostituire il codice che crea il `WSHttpBinding` con il codice seguente:  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- Per il client, nel file di configurazione, aggiornare il  **\<sicurezza >** elemento sotto il  **\<associazione >** elemento come indicato di seguito:  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator" security mode="None" />
    ```  

## <a name="see-also"></a>Vedere anche  
 [Iniziare con le applicazioni WCF](getting-started-tutorial.md)  
 [Guida introduttiva sulla risoluzione dei problemi di WCF](wcf-troubleshooting-quickstart.md)  
 [Risoluzione dei problemi di installazione](troubleshooting-setup-issues.md)
