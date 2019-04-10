---
title: "Procedura: Scoprire se è possibile eseguire un processo di stampa a quest'ora del giorno"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print queues [WPF], timing
- printers [WPF], availability
- print jobs [WPF], timing
ms.assetid: 7e9c8ec1-abf6-4b3d-b1c6-33b35d3c4063
ms.openlocfilehash: 7eed5400744f1010cbf52dc8d3b3d0bc24aa4371
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59326866"
---
# <a name="how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day"></a>Procedura: Scoprire se è possibile eseguire un processo di stampa a quest'ora del giorno
Code di stampa non sono sempre disponibili per 24 ore al giorno. Hanno proprietà ora di inizio e fine che è possibile impostare per renderli disponibili in determinati momenti del giorno. Questa funzionalità è utilizzabile, ad esempio, per riservare una stampante per l'utilizzo esclusivo di un determinato reparto dopo alle 17.00. Tale reparto avrebbe un'altra coda della stampante di altri reparti di manutenzione utilizzano. La coda per gli altri reparti verrebbe impostata sarà disponibile dopo alle 17.00, anche se coda di quella per il reparto può essere impostata per essere sempre disponibile.  
  
 Inoltre, i processi di stampa stessi possono essere impostati come stampabile solo all'interno di un intervallo di tempo specificato.  
  
 Il <xref:System.Printing.PrintQueue> e <xref:System.Printing.PrintSystemJobInfo> classi esposte nel [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] di Microsoft .NET Framework forniscono un mezzo per la verifica in modalità remota se un determinato processo di stampa può stampare su una determinata coda al momento corrente.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente è un esempio che è possibile diagnosticare i problemi di un processo di stampa.  
  
 Esistono due passaggi principali per questo tipo di funzione come indicato di seguito.  
  
1. Lettura di <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> e <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> delle proprietà del <xref:System.Printing.PrintQueue> per determinare se l'ora corrente è tra di essi.  
  
2. Lettura di <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> e <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> delle proprietà del <xref:System.Printing.PrintSystemJobInfo> per determinare se l'ora corrente è tra di essi.  
  
 Ma alcuni problemi sorgono dal fatto che tali proprietà non sono <xref:System.DateTime> oggetti. Sono invece <xref:System.Int32> gli oggetti che esprimono l'ora del giorno come numero di minuti trascorsi dalla mezzanotte. Inoltre, non si tratta mezzanotte nel fuso orario corrente, ma la mezzanotte ora UTC (Coordinated Universal Time).  
  
 Il primo esempio di codice presenta il metodo statico **ReportQueueAndJobAvailability**, che viene passato un <xref:System.Printing.PrintSystemJobInfo> e chiama i metodi helper per determinare se il processo può essere stampato all'ora corrente e, se non, quando è possibile stampare. Si noti che un <xref:System.Printing.PrintQueue> non viene passato al metodo. Infatti, il <xref:System.Printing.PrintSystemJobInfo> include un riferimento alla coda nel relativo <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A> proprietà.  
  
 I metodi subordinati includono l'overload **ReportAvailabilityAtThisTime** metodo che può assumere uno una <xref:System.Printing.PrintQueue> o un <xref:System.Printing.PrintSystemJobInfo> come parametro. È inoltre disponibile un' **TimeConverter**. Tutti questi metodi sono illustrati di seguito.  
  
 Il **ReportQueueAndJobAvailability** metodo inizia con un controllo per verificare se la coda o il processo di stampa non è disponibile in questo momento. Se una di esse è disponibile, quindi controlla se la coda non disponibile. Se non è disponibile, il metodo segnala questo aspetto e il tempo quando la coda sarà nuovamente disponibile. Controlla quindi il processo e se non è disponibile, viene segnalata la volta successiva che estendono quando quando può essere stampato. Infine, il metodo segnala l'ora meno recente quando il processo può essere stampato. Si tratta della seconda dei seguenti due volte.  
  
-   Ora quando la coda di stampa è successivamente disponibile.  
  
-   Ora quando il processo di stampa è successivamente disponibile.  
  
 Quando si segnalano ore del giorno, il <xref:System.DateTime.ToShortTimeString%2A> metodo viene chiamato anche perché questo metodo evita di anni, mesi e giorni dall'output. Non è possibile limitare la disponibilità di una coda di stampa o un processo di stampa per determinati anni, mesi o giorni.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 I due overload del **ReportAvailabilityAtThisTime** metodo sono identici tranne che per il tipo passato ad essi, in modo che solo il <xref:System.Printing.PrintQueue> versione viene presentata di seguito.  
  
> [!NOTE]
>  Il fatto che i metodi sono identici a eccezione di tipo pone la domanda di perché il codice di esempio non crea un metodo generico **ReportAvailabilityAtThisTime\<T >**. Il motivo è che questo metodo deve essere limitato a una classe che ha il **StartTimeOfDay** e **UntilTimeOfDay** le proprietà che chiama il metodo, ma un metodo generico può essere limitato a un singola classe e l'unica classe comune a entrambi <xref:System.Printing.PrintQueue> e <xref:System.Printing.PrintSystemJobInfo> l'ereditarietà di struttura ad albero è <xref:System.Printing.PrintSystemObject> che non dispone di tale proprietà.  
  
 Il **ReportAvailabilityAtThisTime** metodo, come illustrato nell'esempio di codice riportato di seguito, avvia l'inizializzazione di un <xref:System.Boolean> variabile sentinel `true`. Verranno ripristinate a `false`, se la coda non è disponibile.  
  
 Successivamente, il metodo verifica se l'avvio e "until" ora di fine coincidono. In tal caso, la coda è sempre disponibile, in modo che il metodo restituisce `true`.  
  
 Se la coda non è disponibile tutto il tempo, il metodo Usa il metodo statico <xref:System.DateTime.UtcNow%2A> proprietà da ottenere l'ora corrente come un <xref:System.DateTime> oggetto. (Ora locale non è necessaria perché il <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> e <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> sono in formato ora UTC.)  
  
 Tuttavia, queste due proprietà non sono <xref:System.DateTime> oggetti. Sono <xref:System.Int32>s esprime l'ora come numero di minuti trascorsi dalla mezzanotte UTC. Quindi dobbiamo convertire la <xref:System.DateTime> oggetto minuti dopo la mezzanotte. Al termine, il metodo controlla semplicemente per verificare se "ora" sia tra l'inizio della coda e "until" volte, set sentinel su false se "ora" non è compreso tra i due volte e restituisce la sentinella.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 Il **TimeConverter** (metodo), illustrato nell'esempio di codice seguente, non usa metodi introdotti con Microsoft .NET Framework, pertanto la discussione è breve. Il metodo ha un'attività di conversione doppie: deve richiedere un numero intero che esprime minuti dopo la mezzanotte e convertirlo in un momento leggibile dall'utente e si deve convertire nell'ora locale. Ciò è possibile tramite la creazione di un <xref:System.DateTime> oggetto che viene impostato sulla mezzanotte UTC e quindi Usa il <xref:System.DateTime.AddMinutes%2A> metodo per aggiungere i minuti che sono stati passati al metodo. Restituisce un nuovo <xref:System.DateTime> esprime l'ora originale che è stato passato al metodo. Il <xref:System.DateTime.ToLocalTime%2A> metodo quindi converte nell'ora locale.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.DateTime>
- <xref:System.Printing.PrintSystemJobInfo>
- <xref:System.Printing.PrintQueue>
- [Documenti in WPF](documents-in-wpf.md)
- [Cenni preliminari sulla stampa](printing-overview.md)
