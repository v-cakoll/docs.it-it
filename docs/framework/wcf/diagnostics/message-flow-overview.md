---
title: Cenni preliminari sul flusso di messaggi
ms.date: 03/30/2017
ms.assetid: fb0899e1-84cc-4d90-b45b-dc5a50063943
ms.openlocfilehash: d75a535a601612196ef66151a4685723e048848f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772663"
---
# <a name="message-flow-overview"></a>Cenni preliminari sul flusso di messaggi
In un sistema distribuito che contiene servizi interconnessi è necessario determinare relazioni causali tra i servizi. È importante comprendere i vari componenti che appartengono a un flusso di richiesta per supportare scenari critici, ad esempio monitoraggio dello stato, risoluzione dei problemi e analisi della causa radice. Per abilitare la correlazione di tracce tra i vari servizi, in .NET Framework 4 è stato aggiunto supporto tramite le funzionalità seguenti:

-   Traccia analitica: A prestazioni elevate e verbosità ridotta funzionalità di traccia Event Tracing for Windows (ETW).

-   Modello di attività end-to-end per i servizi WCF/WF: Questa funzionalità supporta la correlazione di tracce generate dal <xref:System.ServiceModel> e <xref:System.Workflow.ComponentModel> gli spazi dei nomi.

-   Rilevamento ETW per WF: Questa funzionalità Usa record di rilevamento generati dai servizi WF per fornire visibilità nello stato corrente e lo stato di avanzamento del flusso di lavoro.

 Gli errori registrati in un record di rilevamento o di traccia possono essere usati per individuare difetti del codice o messaggi in formato non corretto. La proprietà ActivityId del nodo relativo alla correlazione nell'intestazione del messaggio dell'evento può essere usata per determinare l'attività in cui si è verificato l'errore. Per abilitare la traccia del flusso di messaggi dall'ID attività, vedere [Configuring Message Flow Tracing](../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md). In questo argomento viene illustrato come abilitare la traccia del flusso di messaggi nel progetto creato nell'Esercitazione introduttiva.

### <a name="to-enable-message-flow-tracing-in-the-getting-started-tutorial"></a>Per abilitare la traccia del flusso di messaggi nell'Esercitazione introduttiva

1. Aprire il Visualizzatore eventi facendo **avviare**, **eseguito**e l'immissione di `eventvwr.exe`.

2. Se non è stata abilitata la traccia analitica, espandere **registri applicazioni e servizi**, **Microsoft**, **Windows**, **Server applicazioni-applicazioni** . Selezionare **View**, **mostrano analitici e i registri Debug**. Fare doppio clic su **analitico** e selezionare **Attiva registro**. Lasciare aperto il Visualizzatore eventi in modo che sia possibile visualizzare le tracce.

3. Aprire l'esempio creato nel [esercitazione introduttiva su](../../../../docs/framework/wcf/getting-started-tutorial.md) in Visual Studio 2012. Si noti che è necessario eseguire Visual Studio 2012 come amministratore in modo che sia possibile creare il servizio. Se si dispone di installare gli esempi WCF, è possibile aprire il [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md), che contiene il progetto completato creato nell'esercitazione.

4. Fare doppio clic sul **assistenza** del progetto e selezionare **Add**, **nuovo elemento**. Selezionare **File di configurazione dell'applicazione** e fare clic su **OK**.

5. Aggiungere il codice seguente al file App.Config creato nel passaggio precedente.

    ```xml
    <system.serviceModel>
      <diagnostics>
        <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>
      </diagnostics>
    </system.serviceModel>
    ```

6. Premere CTRL+F5 per eseguire l'applicazione server senza debug. Eseguire il progetto client facendo clic con il **Client** progetto, quindi selezionando **Debug**, **Avvia nuova istanza**.

7. Per tracciare gli eventi dal client al server, aggiungere il codice seguente al file di configurazione dell'applicazione nel progetto Client.

    ```xml
    <diagnostics>
      <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>
    </diagnostics>
    ```

8. In Program.cs nel client aggiungere l'istruzione Using seguente.

    ```csharp
    using System.Diagnostics;
    ```

9. Nel metodo Main presente nel file program.cs del progetto client impostare il GUID della traccia in modo che venga propagato nel registro eventi.

    ```csharp
    Guid guid = Guid.NewGuid();
    Trace.CorrelationManager.ActivityId = guid;
    ```

10. Aggiornare ed esaminare i **analitico** log.  Cercare gli eventi con ID evento 220.  Selezionare l'evento, quindi scegliere il **dettagli** scheda nel riquadro di anteprima. Questo evento conterrà l'ID di correlazione per l'attività chiamante.

    ```xml
    <Correlation ActivityID="{A066CCF1-8AB3-459B-B62F-F79F957A5036}" />
    ```

    > [!NOTE]
    >  Tutti gli eventi con stesso GUID in ActivityID sono correlati a una richiesta. In questo modo è possibile correlare messaggi tra un client e un servizio specifici. Se il client ha chiamato un altro servizio, lo stesso client potrebbe essere identificato da ActivityID.

11. In alcuni casi l'elemento ActivityID può essere modificato dal GUID originale in un nuovo ActivityID. In questo caso viene generato un evento di trasferimento. L'ID evento è 499 e l'evento conterrà i dati seguenti nell'intestazione.

    ```xml
    <Event xmlns="http://schemas.microsoft.com/win/2004/08/events/event">
        <System>
            <Provider Name="Microsoft-Windows-Application Server-Applications" Guid="{c651f5f6-1c0d-492e-8ae1-b4efd7c9d503}" />
            <EventID>499</EventID>
            ...
            <Correlation ActivityID="{A066CCF1-8AB3-459B-B62F-F79F957A5036}" RelatedActivityID="{85FC0930-9C49-42DA-804B-A7368104BD1B}" />
            ...
       </System>
    </Event>
    ```

    > [!NOTE]
    >  L'evento di trasferimento registra la modifica dell'elemento ActivityID attivo dal GUID specificato come ActivityID al GUID specificato come RelatedActivityID. Dopo che l'evento di trasferimento viene generato, tutti gli eventi conterranno il nuovo GUID come elemento ActivityID.
