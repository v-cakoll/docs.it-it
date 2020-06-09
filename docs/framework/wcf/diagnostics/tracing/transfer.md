---
title: Trasferimento
ms.date: 03/30/2017
ms.assetid: dfcfa36c-d3bb-44b4-aa15-1c922c6f73e6
ms.openlocfilehash: 52b0cf35a2f8bab17252d3711f3143738c2bc39c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84587768"
---
# <a name="transfer"></a>Trasferimento
In questo argomento viene descritto il trasferimento nel modello di traccia attività Windows Communication Foundation (WCF).  
  
## <a name="transfer-definition"></a>Definizione di trasferimento  
 I trasferimenti tra le attività rappresentano le relazioni causali tra eventi nelle attività correlate all'interno di endpoint. Due attività sono correlate con i trasferimenti quando controllano i flussi tra queste attività, ad esempio, una chiamata al metodo che supera i limiti di attività. In WCF, quando i byte sono in ingresso nel servizio, l'attività Listen at viene trasferita all'attività Receive bytes in cui viene creato l'oggetto Message. Per un elenco degli scenari di traccia end-to-end e la rispettiva attività e progettazione di traccia, vedere [scenari di traccia end-to-end](end-to-end-tracing-scenarios.md).  
  
 Per emettere tracce di trasferimento, usare l'impostazione `ActivityTracing` nell'origine di traccia, come illustrato nel codice di configurazione seguente.  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
## <a name="using-transfer-to-correlate-activities-within-endpoints"></a>Utilizzo del trasferimento per correlare le attività all'interno di endpoint  
 Attività e trasferimenti consentono all'utente di individuare probabilisticamente la causa radice di un errore. Se, ad esempio, vi sono trasferimenti tra le attività M e N rispettivamente nei componenti M e N e si verifica un arresto anomalo in N subito dopo il trasferimento a M, se ne può dedurre che ciò è probabilmente dovuto a N che passa indietro i dati a M.  
  
 Una traccia di trasferimento viene emessa dall'attività M all'attività N quando è presente un flusso di controllo tra M e N. N, ad esempio, esegue un lavoro per M a causa di una chiamata al metodo che attraversa i limiti delle attività. N potrebbe esistere già o può essere stato creato. N viene generato da M quando N è una nuova attività che esegue dei lavori per M.  
  
 Un trasferimento da M a N potrebbe non essere seguito da un trasferimento da N a M. Ciò accade perché M può generare lavoro in N e non tiene traccia di quando N lo completa. Di fatto, M può terminare prima che N completi l'attività. Questo errore si verifica nell'attività "Open ServiceHost" (M) che genera le attività del listener (N) e quindi termina. Un ritrasferimento da N a M significa che N ha completato il lavoro correlato a M.  
  
 N può continuare a eseguire altre elaborazioni non correlate a M, ad esempio, un'attività dell'autenticatore esistente (N) che continua a ricevere richieste di accesso (M) da diverse attività di accesso.  
  
 Tra attività M e N non esiste necessariamente una relazione di annidamento. Ciò è dovuto a due ragioni. Innanzitutto, quando l'attività M non controlla l'elaborazione effettiva eseguita in N anche se M ha avviato N. In secondo luogo, quando N esiste già.  
  
## <a name="example-of-transfers"></a>Esempio di trasferimenti  
 Seguono due esempi del trasferimento.  
  
- Quando si crea un host del servizio, il costruttore ottiene il controllo dal codice chiamante oppure il codice chiamante viene trasferito al costruttore. Al termine dell'esecuzione, il costruttore restituisce il controllo al codice chiamante oppure trasferisce di nuovo l'esecuzione al codice chiamante. Questo è il caso di una relazione annidata.  
  
- Quando un listener inizia a elaborare i dati di trasporto, crea un nuovo thread e consegna all'attività di ricezione byte il contesto appropriato per l'elaborazione, passando controllo e dati. Quando quel thread ha terminato di elaborare la richiesta, l'attività di ricezione byte non passa indietro nulla al listener. In questo caso, vi è un trasferimento in ingresso ma nessun trasferimento in uscita della nuova attività del thread. Le due attività sono correlate ma non annidate.  
  
## <a name="activity-transfer-sequence"></a>Sequenza di trasferimento di attività  
 Una sequenza di trasferimento di attività ben formata comprende i passaggi seguenti.  
  
1. Iniziare una nuova attività, che consiste nel selezionare un nuovo gAId.  
  
2. Emettere una traccia di trasferimento a quel nuovo gAId dall'ID attività corrente  
  
3. Impostare il nuovo ID in TLS  
  
4. Emettere una traccia di inizio per indicare l'inizio della nuova attività.  
  
5. Il ritorno all'attività originale è costituito dai passaggi seguenti:  
  
6. Emettere una traccia di trasferimento al gAId originale  
  
7. Emettere una traccia di interruzione per indicare la fine della nuova attività  
  
8. Impostare TLS sul vecchio gAId.  
  
 Nell'esempio di codice seguente viene illustrato come procedere. In questo esempio si presuppone che venga effettuata una chiamata di blocco durante il trasferimento alla nuova attività e sono incluse tracce di sospensione/ripresa.  
  
```csharp
// 0. Create a trace source  
TraceSource ts = new TraceSource("myTS");  

// 1. remember existing ("ambient") activity for clean up  
Guid oldGuid = Trace.CorrelationManager.ActivityId;  
// this will be our new activity  
Guid newGuid = Guid.NewGuid();

// 2. call transfer, indicating that we are switching to the new AID  
ts.TraceTransfer(667, "Transferring.", newGuid);  

// 3. Suspend the current activity.  
ts.TraceEvent(TraceEventType.Suspend, 667, "Suspend: Activity " + i-1);  

// 4. set the new AID in TLS  
Trace.CorrelationManager.ActivityId = newGuid;  

// 5. Emit the start trace  
ts.TraceEvent(TraceEventType.Start, 667, "Boundary: Activity " + i);  

// trace something  
ts.TraceEvent(TraceEventType.Information, 667, "Hello from activity " + i);  

// Perform Work  
// some work.  
// Return  
ts.TraceEvent(TraceEventType.Information, 667, "Work complete on activity " + i);

// 6. Emit the transfer returning to the original activity  
ts.TraceTransfer(667, "Transferring Back.", oldGuid);  

// 7. Emit the End trace  
ts.TraceEvent(TraceEventType.Stop, 667, "Boundary: Activity " + i);  

// 8. Change the tls variable to the original AID  
Trace.CorrelationManager.ActivityId = oldGuid;

// 9. Resume the old activity  
ts.TraceEvent(TraceEventType.Resume, 667, "Resume: Activity " + i-1);  
```  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione delle funzionalità di traccia](configuring-tracing.md)
- [Uso del visualizzatore di tracce dei servizi per la visualizzazione di tracce correlate e la risoluzione dei problemi](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Scenari di analisi end-to-end](end-to-end-tracing-scenarios.md)
- [Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../../service-trace-viewer-tool-svctraceviewer-exe.md)
