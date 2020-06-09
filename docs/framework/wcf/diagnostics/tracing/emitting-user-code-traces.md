---
title: Creazione di tracce di codice utente
ms.date: 03/30/2017
ms.assetid: fa54186a-8ffa-4332-b0e7-63867126fd49
ms.openlocfilehash: e8b2031165a83e24ba15a2fcf847a170f47e696a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589292"
---
# <a name="emitting-user-code-traces"></a>Creazione di tracce di codice utente

Oltre ad abilitare la traccia nella configurazione per raccogliere i dati di strumentazione generati da Windows Communication Foundation (WCF), è anche possibile creare tracce a livello di codice nel codice utente. In questo modo è possibile creare attivamente dati di strumentazione che possono essere successivamente usati a scopo diagnostico. In questo argomento viene illustrata la procedura da seguire.

Inoltre, l'esempio di [estensione della traccia](../../samples/extending-tracing.md) include tutto il codice illustrato nelle sezioni seguenti.

## <a name="creating-a-trace-source"></a>Creazione di un'origine di traccia

Per creare un'origine di traccia dell'utente è possibile usare il codice seguente.

```csharp
TraceSource ts = new TraceSource("myUserTraceSource");
```

## <a name="creating-activities"></a>Creazione di attività

Le attività sono unità logiche  di elaborazione. È possibile creare un'attività per ogni unità di elaborazione principale nella quale si desidera raggruppare le tracce. È possibile creare, ad esempio, un'attività per ogni richiesta inviata al servizio. A tale scopo, eseguire i passaggi seguenti.

1. Salvare l'ID attività nell'ambito.

2. Creare un nuovo ID attività.

3. Eseguire il trasferimento dall'attività nell'ambito alla nuova attività, impostare la nuova attività nell'ambito e creare una traccia di inizio per questa attività.

Nell'esempio di codice seguente viene illustrato come eseguire questa operazione.

```csharp
Guid oldID = Trace.CorrelationManager.ActivityId;
Guid traceID = Guid.NewGuid();
ts.TraceTransfer(0, "transfer", traceID);
Trace.CorrelationManager.ActivityId = traceID; // Trace is static
ts.TraceEvent(TraceEventType.Start, 0, "Add request");
```

## <a name="emitting-traces-within-a-user-activity"></a>Creazione di tracce all'interno di un'attività utente

Il codice seguente crea tracce all'interno di un'attività utente.

```csharp
double value1 = 100.00D;
double value2 = 15.99D;
ts.TraceInformation("Client sends message to Add " + value1 + ", " + value2);
double result = client.Add(value1, value2);
ts.TraceInformation("Client receives Add response '" + result + "'");
```

## <a name="stopping-the-activities"></a>Interruzione delle attività

Per interrompere le attività, tornare alla vecchia attività, interrompere l'ID dell'attività corrente e reimpostare l'ID della vecchia attività nell'ambito.

Nell'esempio di codice seguente viene illustrato come eseguire questa operazione.

```csharp
ts.TraceTransfer(0, "transfer", oldID);
ts.TraceEvent(TraceEventType.Stop, 0, "Add request");
Trace.CorrelationManager.ActivityId = oldID;
```

## <a name="propagating-the-activity-id-to-a-service"></a>Propagazione dell'ID attività a un servizio

Se si imposta l'attributo `propagateActivity` su `true` per l'origine di traccia `System.ServiceModel` in entrambi i file di configurazione del client e del servizio, l'elaborazione del servizio per la richiesta Add si verifica nella stessa attività definita nel client. Se il servizio definisce attività e trasferimenti specifici, le tracce del servizio non vengono visualizzate nell'attività propagata dal client. Vengono invece visualizzate in un'attività correlata mediante tracce di trasferimento all'attività il cui ID viene propagato dal client.

> [!NOTE]
> Se l' `propagateActivity` attributo è impostato `true` su sia nel client che nel servizio, l'attività di ambiente nell'ambito dell'operazione del servizio viene impostata da WCF.

È possibile utilizzare il codice seguente per verificare se un'attività è stata impostata nell'ambito da WCF.

```csharp
// Check if an activity was set in scope by WCF, if it was
// propagated from the client. If not, ( ambient activity is
// equal to Guid.Empty), create a new one.
if(Trace.CorrelationManager.ActivityId == Guid.Empty)
{
    Guid newGuid = Guid.NewGuid();
    Trace.CorrelationManager.ActivityId = newGuid;
}
// Emit your Start trace.
ts.TraceEvent(TraceEventType.Start, 0, "Add Activity");

// Emit the processing traces for that request.
serviceTs.TraceInformation("Service receives Add "
                            + n1 + ", " + n2);
// double result = n1 + n2;
serviceTs.TraceInformation("Service sends Add result" + result);

// Emit the Stop trace and exit the method scope.
ts.TraceEvent(TraceEventType.Stop, 0, "Add Activity");
// return result;
```

## <a name="tracing-exceptions-thrown-in-code"></a>Eccezioni di traccia generate nel codice

Quando si genera un'eccezione nel codice, è anche possibile tracciare l'eccezione a livello di avviso o a un livello superiore usando il codice seguente.

```csharp
ts.TraceEvent(TraceEventType.Warning, 0, "Throwing exception " + "exceptionMessage");
```

## <a name="viewing-user-traces-in-the-service-trace-viewer-tool"></a>Visualizzazione di tracce utente nello strumento di visualizzazione delle tracce dei servizi

In questa sezione sono contenute le schermate delle tracce generate eseguendo l'esempio di [estensione della traccia](../../samples/extending-tracing.md) , quando vengono visualizzate tramite lo [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer. exe)](../../service-trace-viewer-tool-svctraceviewer-exe.md).

Nel diagramma seguente l'attività "Aggiungi richiesta" creata in precedenza è selezionata nel riquadro sinistro. L'attività è riportata insieme ad attività di operazioni matematiche (Divide, Subtract, Multiply) che costituiscono l'applicazione client. Il codice utente ha definito una nuova attività per consentire a ogni operazione di isolare potenziali occorrenze di errore in richieste diverse.

Per illustrare l'utilizzo dei trasferimenti nell'esempio [Extending Tracing](../../samples/extending-tracing.md) , viene creata anche un'attività Calculator che incapsula le quattro richieste di operazione. Per ogni richiesta si verifica un trasferimento dall'attività di calcolo all'attività di richiesta e viceversa (nella figura la traccia è evidenziata nel riquadro in alto a destra).

Quando si seleziona un'attività nel riquadro sinistro, le tracce incluse da questa attività vengono mostrate nel riquadro in alto a destra. Se `propagateActivity` si trova `true` a ogni endpoint nel percorso della richiesta, le tracce nell'attività di richiesta proverranno da tutti i processi che partecipano alla richiesta. In questo esempio, nella quarta colonna del riquadro sono visualizzate tracce relative a entrambi il client e il servizio.

Questa attività mostra l'ordine di elaborazione seguente:

1. Il client invia un messaggio alla richiesta Add.

2. Il servizio riceve il messaggio di richiesta Add.

3. Il servizio invia la risposta Add.

4. Il client riceve la risposta Add.

Tutte queste tracce vengono create a livello di informazioni. Facendo clic su una traccia nel riquadro in alto a destra è possibile visualizzare i dettagli della traccia nel riquadro in basso a destra.

Nel diagramma seguente è inoltre possibile vedere tracce di trasferimento da e verso l'attività di calcolo, nonché due coppie di tracce Start e Stop per ogni attività di richiesta, una per il client e una per il servizio (una per ogni origine di traccia).

![Visualizzatore di tracce: creazione di tracce di codice&#45;utente](media/242c9358-475a-4baf-83f3-4227aa942fcd.gif "242c9358-475a-4baf-83f3-4227aa942fcd") Elenco di attività in base all'ora di creazione (riquadro sinistro) e alle relative attività annidate (riquadro superiore destro)

Se il codice del servizio genera un'eccezione che determina a sua volta la generazione di un'eccezione nel client (ad esempio, quando il client non ha ottenuto la risposta alla richiesta), entrambi i messaggi di errore o di avviso del client e del servizio vengono restituiti nella stessa attività per correlazione diretta. Nell'immagine seguente il servizio genera un'eccezione che indica "il servizio rifiuta di elaborare la richiesta nel codice utente". Il client genera inoltre un'eccezione che indica che il server non è stato in grado di elaborare la richiesta a causa di un errore interno.

Le immagini seguenti mostrano che gli errori tra gli endpoint per una determinata richiesta vengono visualizzati nella stessa attività se l'ID attività della richiesta è stato propagato:

![Screenshot che Mostra gli errori tra gli endpoint per una determinata richiesta.](./media/emitting-user-code-traces/trace-viewer-endpoint-errors.gif)

Facendo doppio clic sull'attività Multiply nel riquadro sinistro è possibile visualizzare il grafico seguente, con le tracce relative all'attività Multiply per ogni processo coinvolto. Si può notare un avviso verificatosi inizialmente nel servizio (eccezione generata), seguito da avvisi ed errori nel client in quanto la richiesta non è stata elaborata. Si può pertanto presupporre la relazione di errore causale tra gli endpoint e derivare la causa radice dell'errore.

La figura seguente mostra una visualizzazione grafico della correlazione degli errori:

![Screenshot che mostra la visualizzazione grafico della correlazione degli errori.](./media/emitting-user-code-traces/trace-viewer-error-correlation.gif)

Per ottenere le tracce precedenti è stato impostato `ActivityTracing` per le origini di traccia dell'utente e `propagateActivity=true` per l'origine di traccia `System.ServiceModel`. Non è stato impostato `ActivityTracing` per l'origine di traccia `System.ServiceModel` per attivare la propagazione di attività codice utente-codice utente. Quando la traccia attività ServiceModel è attiva, l'ID attività definito nel client non viene propagato fino al codice utente del servizio. I trasferimenti, tuttavia, mettono in correlazione le attività del client e del codice utente del servizio alle attività WCF intermedie.

La definizione delle attività e la propagazione dell'ID attività consentono di eseguire la correlazione diretta degli errori sui vari endpoint. In questo modo è possibile individuare più rapidamente la causa radice di un errore.

## <a name="see-also"></a>Vedere anche

- [Estensione della funzionalità di traccia](../../samples/extending-tracing.md)
