---
title: "Procedura: individuare se è possibile eseguire o meno un processo di stampa all'orario indicato"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print queues [WPF], timing
- printers [WPF], availability
- print jobs [WPF], timing
ms.assetid: 7e9c8ec1-abf6-4b3d-b1c6-33b35d3c4063
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ef9da205792823b7069024c5e4a3e9ac80d60a24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day"></a>Procedura: individuare se è possibile eseguire o meno un processo di stampa all'orario indicato
Code di stampa non sono sempre disponibili per 24 ore al giorno. Hanno proprietà ora di inizio e fine che è possibile impostare per renderli disponibili in determinati orari del giorno. Questa funzionalità è utilizzabile, ad esempio, per riservare una stampante per l'utilizzo esclusivo di un determinato reparto dopo le 17.00. Tale reparto avrebbe una coda diversa per la manutenzione della stampante di altri reparti utilizzare. La coda per gli altri reparti verrebbe impostata per essere disponibile dopo le 17.00, mentre coda quella per il reparto può essere impostata per essere sempre disponibile.  
  
 Inoltre, è possono impostare i processi di stampa se stessi come printable solo all'interno di un intervallo di tempo specificato.  
  
 Il <xref:System.Printing.PrintQueue> e <xref:System.Printing.PrintSystemJobInfo> classi esposti nel [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] di [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] consentono di controllare in remoto se un determinato processo di stampa è possibile stampare su una determinata coda al momento corrente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito è riportato un esempio che è possibile diagnosticare i problemi di un processo di stampa.  
  
 Esistono due passaggi principali per questo tipo di funzione come indicato di seguito.  
  
1.  Lettura di <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> e <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> le proprietà del <xref:System.Printing.PrintQueue> per determinare se l'ora corrente è tra di essi.  
  
2.  Lettura di <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> e <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> le proprietà del <xref:System.Printing.PrintSystemJobInfo> per determinare se l'ora corrente è tra di essi.  
  
 Tuttavia verificano complicazioni dal fatto che queste proprietà non sono <xref:System.DateTime> oggetti. Sono invece <xref:System.Int32> oggetti che esprimono l'ora del giorno come il numero di minuti trascorsi dalla mezzanotte. Inoltre, non si tratta mezzanotte nel fuso orario corrente, ma la mezzanotte ora UTC (Coordinated Universal Time).  
  
 Il primo esempio di codice presenta il metodo statico **ReportQueueAndJobAvailability**, che viene passato un <xref:System.Printing.PrintSystemJobInfo> e chiama i metodi helper per determinare se il processo può essere stampato all'ora corrente e, se non, quando è possibile stampare. Si noti che un <xref:System.Printing.PrintQueue> non viene passato al metodo. In questo modo il <xref:System.Printing.PrintSystemJobInfo> include un riferimento alla coda nel relativo <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A> proprietà.  
  
 I metodi subordinati includono il metodo di overload **ReportAvailabilityAtThisTime** metodo che può accettare un <xref:System.Printing.PrintQueue> o <xref:System.Printing.PrintSystemJobInfo> come parametro. È inoltre disponibile un **TimeConverter**. Tutti questi metodi sono descritti di seguito.  
  
 Il **ReportQueueAndJobAvailability** metodo inizia con un controllo per verificare se la coda o il processo di stampa non è disponibile in questo momento. Se nessuno dei due non è disponibile, viene quindi verificato se la coda non disponibile. Se non è disponibile, il metodo segnala tale situazione e il tempo quando la coda sarà nuovamente disponibile. Verifica quindi il processo e se non è disponibile, viene segnalato al successivo quando span quando è possibile stampare. Infine, il metodo segnala l'ora meno recente quando il processo è possibile stampare. Si tratta della seconda dei seguenti due volte.  
  
-   Ora quando la coda di stampa è successivamente disponibile.  
  
-   Ora quando il processo di stampa è disponibile.  
  
 Quando si segnalano ore del giorno, il <xref:System.DateTime.ToShortTimeString%2A> metodo viene chiamato anche il metodo che elimina l'anni, mesi e giorni dall'output. In particolari anni, mesi o giorni, è possibile limitare la disponibilità di una coda di stampa o un processo di stampa.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 I due overload del **ReportAvailabilityAtThisTime** metodo sono identiche ad eccezione del tipo passato a essi in modo che solo il <xref:System.Printing.PrintQueue> versione viene presentata di seguito.  
  
> [!NOTE]
>  Il fatto che i metodi sono identici ad eccezione di tipo genera alla domanda perché il codice di esempio non crea un metodo generico **ReportAvailabilityAtThisTime\<T >**. Il motivo è che tale metodo deve essere limitato a una classe che ha il **StartTimeOfDay** e **UntilTimeOfDay** proprietà che chiama il metodo, ma un metodo generico può essere limitato a un singola classe e l'unica classe comune a entrambi <xref:System.Printing.PrintQueue> e <xref:System.Printing.PrintSystemJobInfo> nell'ereditarietà a struttura ad albero è <xref:System.Printing.PrintSystemObject> che non dispone di tali proprietà.  
  
 Il **ReportAvailabilityAtThisTime** metodo, come illustrato nell'esempio di codice riportato di seguito, avvia l'inizializzazione di un <xref:System.Boolean> variabile sentinel per `true`. Verranno ripristinata `false`, se la coda non è disponibile.  
  
 Successivamente, il metodo controlla se l'inizio e "fino a quando non" volte identico. In tal caso, la coda è sempre disponibile, il metodo restituisce `true`.  
  
 Se la coda non è disponibile tutto il tempo, il metodo utilizza il metodo statico <xref:System.DateTime.UtcNow%2A> proprietà da ottenere l'ora corrente come un <xref:System.DateTime> oggetto. (Ora locale non è necessaria perché il <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> e <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> sono in formato ora UTC.)  
  
 Tuttavia, queste due proprietà non sono <xref:System.DateTime> oggetti. Sono <xref:System.Int32>s esprime l'ora come numero di minuti dopo la mezzanotte ora UTC. Pertanto è necessario convertire il nostro <xref:System.DateTime> oggetto minuti trascorsi dalla mezzanotte. Una volta effettuata questa operazione, il metodo controlla semplicemente per verificare se "ora" sia tra l'inizio della coda e "volte, imposta sentinel su false se"ora"non è compreso tra due volte e restituisce sentinel fino a".  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 Il **TimeConverter** metodo, come illustrato nell'esempio di codice riportato di seguito, non utilizzare alcun metodo introdotto con [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], pertanto la discussione è breve. Il metodo ha un'attività di conversione doppie: deve accettare un numero intero che esprime minuti dopo la mezzanotte e convertirlo in un momento leggibile e questo deve convertire l'ora locale. Esegue questa operazione creando innanzitutto un <xref:System.DateTime> oggetto che viene impostato sulla mezzanotte ora UTC, quindi viene utilizzato il <xref:System.DateTime.AddMinutes%2A> metodo per aggiungere i minuti che sono stati passati al metodo. Restituisce un nuovo <xref:System.DateTime> esprime l'ora originale è stato passato al metodo. Il <xref:System.DateTime.ToLocalTime%2A> metodo converte quindi l'ora locale.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.DateTime>  
 <xref:System.Printing.PrintSystemJobInfo>  
 <xref:System.Printing.PrintQueue>  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Panoramica della stampa](../../../../docs/framework/wpf/advanced/printing-overview.md)
