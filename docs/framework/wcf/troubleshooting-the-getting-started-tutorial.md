---
title: Risolvere i problemi relativi alle esercitazioni introduzione a Windows Communication Foundation
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 92e986370fe1b6e067d9f8aebc73179c1ac6a20f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183097"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>Risolvere i problemi relativi alle esercitazioni introduzione a Windows Communication Foundation

In questo articolo vengono fornite le soluzioni per i problemi e gli errori più comuni che è possibile affrontare quando si esegue la procedura descritta [nell'esercitazione: Introduzione alle applicazioni Windows Communication Foundation](getting-started-tutorial.md).
  
## <a name="common-problems"></a>Problemi frequenti

**Non riesco a trovare i file di progetto sul mio disco rigido.**

 Visual Studio salva i file di progetto in *C:\\&lt;&gt;*.  

**Impossibile trovare il file *App.config* generato da *Svcutil.exe*.**

 In Visual Studio, la finestra **Aggiungi elemento esistente** visualizza solo i file con le estensioni seguenti per impostazione predefinita:

- *Cs*
- *resx*
- *.settings (impostazioni)*
- *Xsd*
- *wsdl*

Per visualizzare tutti i tipi di file, selezionare **Tutti i file\*( .\*)** nell'elenco a discesa nell'angolo inferiore destro della finestra Aggiungi elemento **esistente.**  
  
## <a name="common-errors"></a>Errori comuni

### <a name="compile-the-service-application"></a>Compilare l'applicazione di servizioCompile the service application

**Errore BC30420 'Sub Main' non trovato in 'GettingStartedHost.Module1'.**

Il punto di ingresso non è corretto per l'applicazione Visual Basic. Apportare le seguenti modifiche:

   1. Nella finestra **Esplora soluzioni** selezionare la cartella **GettingStartedHost** e quindi **scegliere Proprietà** dal menu di scelta rapida.
    a. Nella finestra **GettingStartedHost,** per **oggetto Startup**, selezionare **Service.Program** (o il punto di ingresso per l'applicazione specifica) dall'elenco.
    b. Dal menu principale, selezionare**Salva tutto** **.** > 

### <a name="run-the-service-application"></a>Eseguire l'applicazione di servizioRun the service application

**HTTP non è stato\/in grado di registrare l'URL 'http: /:8000/GettingStarted/CalculatorService'. Il processo non dispone dei diritti di accesso a questo spazio dei nomi.**

 Per un accesso corretto, avviare il processo che ospita il servizio Windows Communication Foundation (WCF) con privilegi amministrativi:For proper access, start the process hosting the Windows Communication Foundation (WCF) service with administrative privileges:

- Per Visual Studio: selezionare il programma di Visual Studio nel menu **Start** e quindi selezionare **Altro** > **Esegui come amministratore** dal menu di scelta rapida.
- Per una finestra della console: selezionare **Prompt dei comandi** nel menu **Start,** quindi selezionare **Altro** > amministratore Esegui**come** amministratore dal menu di scelta rapida.
- Per Esplora risorse: selezionare l'eseguibile, quindi scegliere **Esegui come amministratore** dal menu di scelta rapida.

### <a name="compile-the-client-application"></a>Compilare l'applicazione clientCompile the client application

**'CalculatorClient', non contiene una\<definizione per ' nome\<metodo>' e non è stato trovato alcun metodo di estensione ' nome metodo>' che accetta un primo argomento di tipo 'CalculatorClient' (manca una direttiva using o un riferimento all'assembly?)**  

Solo i metodi contrassegnati `ServiceOperationAttribute` con l'attributo vengono esposti pubblicamente. Se si omettere `ServiceOperationAttribute` l'attributo `ICalculator` da un metodo nell'interfaccia, viene visualizzato questo messaggio di errore durante la compilazione.  

**Impossibile trovare il nome del tipo o dello spazio dei nomi 'CalculatorClient' (manca una direttiva using o un riferimento all'assembly?)**

 Questo errore viene visualizzato se non si aggiunge il file *generatedProxy.cs* (o *generatedProxy.vb*) al progetto client quando vengono generati con lo strumento *Svcutil.exe.*  

### <a name="run-the-client-application"></a>Eseguire l'applicazione client

**Eccezione non gestita: System.ServiceModel.EndpointNotFoundException: Impossibile\/connettersi a 'http: /localhost:8000/GettingStarted/CalculatorService'. Codice di errore TCP 10061: Impossibile creare alcuna connessione perché il computer di destinazione l'ha rifiutata attivamente.**

Questo errore si verifica se si esegue l'applicazione client senza avviare prima il servizio. Eseguire innanzitutto l'applicazione host per avviare il servizio, quindi eseguire l'applicazione client.

### <a name="use-the-svcutilexe-tool"></a>Utilizzare lo strumento Svcutil.exe

**'Svcutil' non è riconosciuto come comando interno o esterno, programma utilizzabile o file batch.**

 *Svcutil.exe* deve essere nel percorso di sistema. La soluzione più semplice consiste nell'utilizzare il prompt dei comandi di Visual Studio.The easiest solution is to use the Visual Studio command prompt. Dal menu **Start** , selezionare la directory **di Visual Studio \<versione>** , quindi selezionare Prompt dei comandi per sviluppatori per la versione vs ** \<>**. Questo prompt dei comandi imposta il percorso di sistema per i percorsi corretti per tutti gli strumenti forniti come parte di Visual Studio.This command prompt sets the system path to the correct locations for all tools shipped as part of Visual Studio.  
  
### <a name="run-the-service-and-client-applications"></a>Eseguire il servizio e le applicazioni clientRun the service and client applications

**System.ServiceModel.Security.SecurityNegotiationException: negoziazione di sicurezza\/SOAP con 'http: /localhost:8000/GettingStarted/CalculatorService' per la destinazione 'http:\//localhost:8000/GettingStarted/CalculatorService' non riuscita**  

Questo errore si verifica in un computer appartenente a un dominio che non dispone di connettività di rete. Connettere il computer alla rete o disattivare la sicurezza sia per il servizio che per il client.

Per disattivare la sicurezza:

- Per il servizio, sostituire il `WSHttpBinding` codice che crea il codice con il codice seguente:For the service, replace the code that creates the with the following code:  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- Per il client, nel file ** \<** di configurazione, aggiornare l'elemento di>di sicurezza nell'elemento ** \<>** di associazione come segue:  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator" security mode="None" />
    ```  

## <a name="see-also"></a>Vedere anche  
 [Introduzione alle applicazioni WCFGet started with WCF applications](getting-started-tutorial.md)  
 [Guida introduttiva alla risoluzione dei problemi di WCFWCF troubleshooting quickstart](wcf-troubleshooting-quickstart.md)  
 [Risoluzione dei problemi di installazione](troubleshooting-setup-issues.md)
