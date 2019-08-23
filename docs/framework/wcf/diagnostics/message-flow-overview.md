---
title: Cenni preliminari sul flusso di messaggi
ms.date: 03/30/2017
ms.assetid: fb0899e1-84cc-4d90-b45b-dc5a50063943
ms.openlocfilehash: cee579f272700ca37228bacecdf387d03637610a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963049"
---
# <a name="message-flow-overview"></a>Cenni preliminari sul flusso di messaggi
In un sistema distribuito che contiene servizi interconnessi è necessario determinare relazioni causali tra i servizi. È importante comprendere i vari componenti che appartengono a un flusso di richiesta per supportare scenari critici, ad esempio monitoraggio dello stato, risoluzione dei problemi e analisi della causa radice. Per abilitare la correlazione di tracce tra i vari servizi, in .NET Framework 4 è stato aggiunto supporto tramite le funzionalità seguenti:

- Traccia analitica: Funzionalità di traccia a prestazioni elevate e a basso livello di dettaglio con Event Tracing for Windows (ETW).

- Modello di attività end-to-end per i servizi WCF/WF: Questa funzionalità supporta la <xref:System.ServiceModel> correlazione delle tracce generate dagli spazi dei nomi e. <xref:System.Workflow.ComponentModel>

- Rilevamento ETW per WF: Questa funzionalità Usa i record di rilevamento generati dai servizi WF per fornire visibilità sullo stato corrente e sullo stato di avanzamento del flusso di lavoro.

 Gli errori registrati in un record di rilevamento o di traccia possono essere usati per individuare difetti del codice o messaggi in formato non corretto. La proprietà ActivityId del nodo relativo alla correlazione nell'intestazione del messaggio dell'evento può essere usata per determinare l'attività in cui si è verificato l'errore. Per abilitare la traccia del flusso di messaggi in base all'ID attività, vedere [configurazione della traccia del flusso di messaggi](../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md). In questo argomento viene illustrato come abilitare la traccia del flusso di messaggi nel progetto creato nell'Esercitazione introduttiva.

### <a name="to-enable-message-flow-tracing-in-the-getting-started-tutorial"></a>Per abilitare la traccia del flusso di messaggi nell'Esercitazione introduttiva

1. Aprire Visualizzatore eventi facendo clic su **Start**, **Esegui**e immettendo `eventvwr.exe`.

2. Se non è stata abilitata la traccia analitica, espandere **registri applicazioni e servizi**, **Microsoft**, **Windows**, **server applicazioni-applicazioni**. Selezionare **Visualizza**, Mostra **log analitici e di debug**. Fare clic con il pulsante destro del mouse su analitico e selezionare **Abilita log**. Lasciare aperto il Visualizzatore eventi in modo che sia possibile visualizzare le tracce.

3. Aprire l'esempio creato nell' [esercitazione Introduzione](../../../../docs/framework/wcf/getting-started-tutorial.md) in Visual Studio 2012. Si noti che è necessario eseguire Visual Studio 2012 come amministratore in modo che sia possibile creare il servizio. Se sono stati installati gli esempi WCF, è possibile aprire il [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md), che contiene il progetto completato creato nell'esercitazione.

4. Fare clic con il pulsante destro del mouse sul progetto di **servizio** e scegliere **Aggiungi**, **nuovo elemento**. Selezionare **file di configurazione dell'applicazione** e fare clic su **OK**.

5. Aggiungere il codice seguente al file App.Config creato nel passaggio precedente.

    ```xml
    <system.serviceModel>
      <diagnostics>
        <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>
      </diagnostics>
    </system.serviceModel>
    ```

6. Premere CTRL+F5 per eseguire l'applicazione server senza debug. Per eseguire il progetto client, fare clic con il pulsante destro del mouse sul progetto **client** e scegliere **debug**, **Avvia nuova istanza**.

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

10. Aggiornare ed esaminare il registro analitico.  Cercare gli eventi con ID evento 220.  Selezionare l'evento e fare clic sulla scheda **Dettagli** nel riquadro di anteprima. Questo evento conterrà l'ID di correlazione per l'attività chiamante.

    ```xml
    <Correlation ActivityID="{A066CCF1-8AB3-459B-B62F-F79F957A5036}" />
    ```

    > [!NOTE]
    > Tutti gli eventi con stesso GUID in ActivityID sono correlati a una richiesta. In questo modo è possibile correlare messaggi tra un client e un servizio specifici. Se il client ha chiamato un altro servizio, lo stesso client potrebbe essere identificato da ActivityID.

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
    > L'evento di trasferimento registra la modifica dell'elemento ActivityID attivo dal GUID specificato come ActivityID al GUID specificato come RelatedActivityID. Dopo che l'evento di trasferimento viene generato, tutti gli eventi conterranno il nuovo GUID come elemento ActivityID.
