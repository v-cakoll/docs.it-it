---
title: Risolvere i problemi relativi alle esercitazioni introduttive Windows Communication Foundation
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 10a2f8f718d802a7aab067b882f0d5cf3dc28dca
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928572"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>Risolvere i problemi relativi alle esercitazioni introduttive Windows Communication Foundation

Questo articolo fornisce soluzioni per i problemi e gli errori più comuni che possono verificarsi quando si seguono i passaggi [dell'esercitazione: Inizia a usare Windows Communication Foundation applicazioni](getting-started-tutorial.md). 
  
## <a name="common-problems"></a>Problemi comuni

**Non è possibile trovare i file di progetto nel disco rigido.**

 Visual Studio salva i file di progetto nel *\\nome&gt;utente C:\Users&lt;\source\repos*.  

**Non è possibile trovare il file *app. config* generato da *Svcutil. exe*.**

 In Visual Studio la finestra **Aggiungi elemento esistente** Visualizza solo i file con le estensioni seguenti per impostazione predefinita: 

- *.cs* 
- *.resx* 
- *.settings*
- *.xsd* 
- *.wsdl*

Per visualizzare tutti i tipi di file, selezionare **tutti\*i\*file (.)** nell'elenco a discesa nell'angolo inferiore destro della finestra **Aggiungi elemento esistente** .  
  
## <a name="common-errors"></a>Errori comuni

### <a name="compile-the-service-application"></a>Compilare l'applicazione di servizio 

**Errore BC30420' Sub Main ' non trovato in ' GettingStartedHost. Module1'.**

Il punto di ingresso non è corretto per l'applicazione Visual Basic. Apportare le modifiche seguenti:

   1. Nella finestra di **Esplora soluzioni** selezionare la cartella **GettingStartedHost** e quindi selezionare **proprietà** dal menu di scelta rapida.
    a. Nella finestra **GettingStartedHost** , per **oggetto di avvio**, selezionare **Service. Program** (oppure il punto di ingresso per l'applicazione specifica) dall'elenco. 
    b. Dal menu principale selezionare **file** > **Salva tutto**.

### <a name="run-the-service-application"></a>Eseguire l'applicazione di servizio 

**Http non è stato in grado di registrare\/l'URL ' http:/+: 8000/GettingStarted/CalculatorService '. Il processo non dispone dei diritti di accesso a questo spazio dei nomi.** 

 Per accedere correttamente, avviare il processo che ospita il servizio Windows Communication Foundation (WCF) con privilegi amministrativi:

- Per Visual Studio: Selezionare il programma di Visual Studio nel menu **Start** , quindi selezionare **altro** > **Esegui come amministratore** dal menu di scelta rapida.
- Per una finestra della console: Selezionare **prompt dei comandi** nel **menu Start** , quindi selezionare **altro** > **Esegui come amministratore** dal menu di scelta rapida.
- Per Esplora risorse: Selezionare il file eseguibile, quindi scegliere **Esegui come amministratore** dal menu di scelta rapida.

### <a name="compile-the-client-application"></a>Compilare l'applicazione client

**' CalculatorClient ' non contiene una definizione per '\<Method name >' e non è stato trovato alcun metodo di estensione '\<Method name >' che accetta un primo argomento di tipo ' CalculatorClient ' (manca una direttiva using o un riferimento ad assembly**  

Vengono esposti pubblicamente solo i metodi contrassegnati `ServiceOperationAttribute` con l'attributo. Se si omette l' `ServiceOperationAttribute` attributo da un metodo nell'interfaccia `ICalculator` , viene visualizzato questo messaggio di errore durante la compilazione.  

**Impossibile trovare il tipo o il nome dello spazio dei nomi ' CalculatorClient '. manca una direttiva using o un riferimento a un assembly.**

 Questo errore viene visualizzato se non si aggiunge il file *generatedProxy.cs* (o *generatedProxy. vb*) al progetto client quando sono stati generati con lo strumento *Svcutil. exe* .  

### <a name="run-the-client-application"></a>Eseguire l'applicazione client

**Eccezione non gestita: System.ServiceModel.EndpointNotFoundException: Non è stato possibile connettersi a'\/http:/localhost: 8000/GettingStarted/CalculatorService '. Codice di errore TCP 10061: Non è stato possibile connettersi perché il computer di destinazione lo ha rifiutato attivamente.**

Questo errore si verifica se si esegue l'applicazione client senza prima avviare il servizio. Eseguire innanzitutto l'applicazione host per avviare il servizio, quindi eseguire l'applicazione client.

### <a name="use-the-svcutilexe-tool"></a>Utilizzare lo strumento Svcutil. exe
   
**' Svcutil ' non è riconosciuto come comando interno o esterno, programma eseguibile o file batch.**

 *Svcutil. exe* deve trovarsi nel percorso di sistema. La soluzione più semplice consiste nell'usare il prompt dei comandi di Visual Studio. Dal menu **Start** , selezionare la **versione di Visual \<Studio >** directory  **\<** , quindi selezionare prompt dei comandi per gli sviluppatori per Visual Studio Version >. Questo prompt dei comandi imposta il percorso di sistema sui percorsi corretti per tutti gli strumenti forniti come parte di Visual Studio.  
  
### <a name="run-the-service-and-client-applications"></a>Eseguire il servizio e le applicazioni client

**System.ServiceModel.Security.SecurityNegotiationException: Negoziazione di sicurezza SOAP con ' http\/:/localhost: 8000/GettingStarted/CalculatorService ' per la destinazione '\/http:/localhost: 8000/GettingStarted/CalculatorService ' non riuscita**  

Questo errore si verifica in un computer aggiunto a un dominio che non dispone di connettività di rete. Connettere il computer alla rete o disattivare la sicurezza sia per il servizio che per il client. 

Per disattivare la sicurezza:

- Per il servizio, sostituire il codice che crea l' `WSHttpBinding` oggetto con il codice seguente:  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- Per il client, nel file di configurazione aggiornare l'  **\<elemento Security >** nell'  **\<elemento binding >** , come indicato di seguito:  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator" security mode="None" />
    ```  

## <a name="see-also"></a>Vedere anche  
 [Introduzione alle applicazioni WCF](getting-started-tutorial.md)  
 [Guida introduttiva alla risoluzione dei problemi di WCF](wcf-troubleshooting-quickstart.md)  
 [Risoluzione dei problemi di installazione](troubleshooting-setup-issues.md)
