---
title: 'Procedura: diagnosticare processi di stampa problematici'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- troubleshooting print job problems [WPF]
- print jobs [WPF], troubleshooting
- print jobs [WPF], diagnosing problems
ms.assetid: b081a170-84c6-48f9-a487-5766a8d58a82
ms.openlocfilehash: 15de5d9ec8dc4016753b9d4cbed6fb0c64571774
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186036"
---
# <a name="how-to-diagnose-problematic-print-job"></a>Procedura: diagnosticare processi di stampa problematici
Gli amministratori di rete fanno spesso fronte ai reclami degli utenti su processi di stampa lenti o che non vengono eseguiti affatto. Il set completo di proprietà dei processi di stampa esposte nelle API di Microsoft .NET Framework fornisce un mezzo per eseguire una diagnosi remota rapida dei processi di stampa.  
  
## <a name="example"></a>Esempio  
 Di seguito sono indicati i passaggi principali per la creazione di questo tipo di utilità.  
  
1. Identificare il processo di stampa oggetto del reclamo dell'utente. Gli utenti spesso non sono in grado di eseguire questa verifica con precisione. Non conoscono i nomi dei server di stampa o delle stampanti. Possono descrivere la posizione della stampante in una terminologia diversa da quella utilizzata nell'impostazione della relativa <xref:System.Printing.PrintQueue.Location%2A> proprietà. È consigliabile quindi generare un elenco dei processi inviati dall'utente. Nel caso ci siano più processi, la comunicazione tra l'utente e l'amministratore del sistema di stampa può essere quindi usata per individuare il processo problematico. Di seguito sono indicati i passaggi secondari.  
  
    1. Ottenere un elenco di tutti i server di stampa.  
  
    2. Riprodurre il ciclo dei server per eseguire una query sulle code di stampa.  
  
    3. In ogni passaggio del ciclo del server, riprodurre il ciclo di tutte le code del server per eseguire query sui processi.  
  
    4. In ogni passaggio del ciclo di code, eseguire il ciclo dei processi e raccogliere informazioni di identificazione su quelli che sono stati inviati dall'utente del reclamo.  
  
2. Quando viene individuato il processo di stampa problematico, esaminare le proprietà rilevanti per vedere quale potrebbe essere la causa del problema. Ad esempio, se si tratta di un errore di stato del processo oppure la stampante che gestisce la coda è passata alla modalità offline prima della stampa.  
  
 Il codice riportato di seguito include una serie di esempi di codice. Il primo esempio di codice contiene il ciclo tra le code di stampa. (Passaggio 1c precedente.) La `myPrintQueues` variabile <xref:System.Printing.PrintQueueCollection> è l'oggetto per il server di stampa corrente.  
  
 L'esempio di codice inizia aggiornando <xref:System.Printing.PrintQueue.Refresh%2A?displayProperty=nameWithType>l'oggetto coda di stampa corrente con . Ciò garantisce che le proprietà dell'oggetto rappresentano accuratamente lo stato della stampante fisica rappresentata. L'applicazione ottiene quindi la raccolta dei processi <xref:System.Printing.PrintQueue.GetPrintJobInfoCollection%2A>di stampa attualmente presenti nella coda di stampa utilizzando .  
  
 Successivamente l'applicazione scorre <xref:System.Printing.PrintSystemJobInfo> in ciclo <xref:System.Printing.PrintSystemJobInfo.Submitter%2A> la raccolta e confronta ogni proprietà con l'alias dell'utente che si lamenta. Se ci sono corrispondenze, l'applicazione aggiunge le informazioni di identificazione sul processo alla stringa che verrà visualizzata. Le variabili `userName` e `jobList` vengono inizializzate prima nell'applicazione.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#enumeratejobsinqueues)]
 [!code-csharp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#enumeratejobsinqueues)]
 [!code-vb[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#enumeratejobsinqueues)]  
  
 L'esempio di codice successivo preleva l'applicazione al passaggio 2. (Vedere sopra.) Il processo problematico è stato identificato e l'applicazione richiede le informazioni che lo identificheranno. Da queste informazioni <xref:System.Printing.PrintServer> <xref:System.Printing.PrintQueue>crea <xref:System.Printing.PrintSystemJobInfo> , , e gli oggetti.  
  
 A questo punto l'applicazione contiene una struttura ramificata corrispondente ai due modi di controllo dello stato del processo di stampa:  
  
- È possibile leggere i <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> flag della <xref:System.Printing.PrintJobStatus>proprietà che è di tipo .  
  
- È possibile leggere ogni <xref:System.Printing.PrintSystemJobInfo.IsBlocked%2A> proprietà <xref:System.Printing.PrintSystemJobInfo.IsInError%2A>rilevante come e .  
  
 In questo esempio vengono illustrati entrambi i metodi, pertanto all'utente è stato precedentemente richiesto quale <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> metodo utilizzare e ha risposto con "Y" se desiderava utilizzare i flag della proprietà. Per i dettagli dei due metodi, vedere di seguito. Infine, l'applicazione usa un metodo denominato **ReportQueueAndJobAvailability** per segnalare se il processo può essere stampato all'ora indicata. Questo metodo viene illustrato in [Individuare se è possibile eseguire o meno un processo di stampa all'orario indicato](how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day.md).  
  
 [!code-cpp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#identifyanddiagnoseproblematicjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#identifyanddiagnoseproblematicjob)]
 [!code-vb[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#identifyanddiagnoseproblematicjob)]  
  
 Per controllare lo stato del <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> processo di stampa utilizzando i flag della proprietà, controllare ogni flag pertinente per vedere se è impostato. Il metodo standard per verificare se un bit è impostato in un set di flag di bit consiste nell'eseguire un'operazione di AND logico con il set di flag come uno degli operandi e il flag stesso come altro operando. Poiché il flag stesso ha un solo bit impostato, il risultato dell'AND logico è che, al massimo, è impostato quello stesso bit. Per verificare se lo è o meno, confrontare il risultato dell’AND logico con il flag stesso. Per ulteriori informazioni, vedere <xref:System.Printing.PrintJobStatus>, l'operatore& [(Riferimenti per C)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)e <xref:System.FlagsAttribute>.  
  
 Per ogni attributo il cui bit è impostato, il codice lo riporta allo schermo della console e talvolta suggerisce un modo per rispondere. Il metodo **HandlePausedJob** che viene chiamato se il processo o la coda è in pausa è illustrato di seguito.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobattributes)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobattributes)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobattributes)]  
  
 Per controllare lo stato del processo di stampa usando proprietà separate, è sufficiente leggere tutte le proprietà e, se la proprietà è `true`, visualizzarla nello schermo della console e suggerire possibilmente una modalità di risposta. Il metodo **HandlePausedJob** che viene chiamato se il processo o la coda è in pausa è illustrato di seguito.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobproperties)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobproperties)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobproperties)]  
  
 Il metodo **HandlePausedJob** consente all'utente dell'applicazione di riprendere i processi sospesi in modalità remota. Poiché potrebbe esserci un motivo valido per cui è stata sospesa la coda di stampa, il metodo inizia richiedendo all'utente conferma sul riavvio. Se la risposta è "Y", viene chiamato il <xref:System.Printing.PrintQueue.Resume%2A?displayProperty=nameWithType> metodo .  
  
 Successivamente, verrà richiesto all'utente di decidere se deve essere ripreso il processo stesso, nel caso sia stato sospeso indipendentemente dalla coda di stampa. (Confronta <xref:System.Printing.PrintQueue.IsPaused%2A?displayProperty=nameWithType> <xref:System.Printing.PrintSystemJobInfo.IsPaused%2A?displayProperty=nameWithType>e .) Se la risposta è "Y", allora <xref:System.Printing.PrintSystemJobInfo.Resume%2A?displayProperty=nameWithType> viene chiamato; in <xref:System.Printing.PrintSystemJobInfo.Cancel%2A> caso contrario viene chiamato.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#HandlePausedJob](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#handlepausedjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#HandlePausedJob](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#handlepausedjob)]
 [!code-vb[DiagnoseProblematicPrintJob#HandlePausedJob](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#handlepausedjob)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Printing.PrintJobStatus>
- <xref:System.Printing.PrintSystemJobInfo>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintQueue>
- [Operatore& (Riferimenti per C](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [Documenti in WPF](documents-in-wpf.md)
- [Cenni preliminari sulla stampa](printing-overview.md)
