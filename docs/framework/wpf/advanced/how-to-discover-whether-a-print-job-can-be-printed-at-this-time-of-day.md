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
ms.openlocfilehash: 859dc75169e443d07361951692a428507886fa2e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947804"
---
# <a name="how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day"></a>Procedura: Scoprire se è possibile eseguire un processo di stampa a quest'ora del giorno
Le code di stampa non sono sempre disponibili per 24 ore al giorno. Hanno le proprietà dell'ora di inizio e di fine che possono essere impostate in modo da renderle non disponibili in determinati orari del giorno. Questa funzionalità può essere usata, ad esempio, per riservare una stampante per l'uso esclusivo di un determinato reparto dopo le 17:00. Tale reparto avrebbe una coda diversa per la manutenzione della stampante rispetto ad altri reparti. La coda per gli altri reparti verrà impostata in modo da non essere disponibile dopo le 17:00, mentre la coda per il reparto favorito potrebbe essere impostata in modo che sia sempre disponibile.  
  
 Inoltre, i processi di stampa possono essere impostati in modo da essere stampabili solo entro un intervallo di tempo specificato.  
  
 Le <xref:System.Printing.PrintQueue> classi <xref:System.Printing.PrintSystemJobInfo> e esposte nelle API di Microsoft .NET Framework forniscono un mezzo per verificare in remoto se un determinato processo di stampa è in grado di stampare in una determinata coda all'ora corrente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente è riportato un esempio in grado di diagnosticare i problemi relativi a un processo di stampa.  
  
 Esistono due passaggi principali per questo tipo di funzione, come indicato di seguito.  
  
1. Leggere le <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> proprietà <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> e dell'oggetto <xref:System.Printing.PrintQueue> per determinare se l'ora corrente è compresa tra di esse.  
  
2. Leggere le <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> proprietà <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> e dell'oggetto <xref:System.Printing.PrintSystemJobInfo> per determinare se l'ora corrente è compresa tra di esse.  
  
 Tuttavia, le complicazioni derivano dal fatto che <xref:System.DateTime> queste proprietà non sono oggetti. Sono <xref:System.Int32> invece oggetti che esprimono l'ora del giorno come numero di minuti dalla mezzanotte. Inoltre, questa non è la mezzanotte nel fuso orario corrente, ma la mezzanotte UTC (Coordinated Universal Time).  
  
 Il primo esempio di codice presenta il metodo statico **ReportQueueAndJobAvailability**, a cui viene <xref:System.Printing.PrintSystemJobInfo> passato un oggetto e chiama metodi helper per determinare se il processo è in grado di stampare nell'ora corrente e, in caso contrario, quando è in grado di stampare. Si noti che <xref:System.Printing.PrintQueue> un oggetto non viene passato al metodo. Questo è dovuto al <xref:System.Printing.PrintSystemJobInfo> fatto che include un riferimento alla coda nella <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A> relativa proprietà.  
  
 I metodi subordinati includono il metodo **ReportAvailabilityAtThisTime** di overload che può assumere <xref:System.Printing.PrintQueue> o <xref:System.Printing.PrintSystemJobInfo> come parametro. Esiste anche un **TimeConverter. ConvertToLocalHumanReadableTime**. Tutti questi metodi sono descritti di seguito.  
  
 Il metodo **ReportQueueAndJobAvailability** inizia con il controllo per verificare se la coda o il processo di stampa non è disponibile in questo momento. Se una di esse non è disponibile, verifica se la coda non è disponibile. Se non è disponibile, il metodo segnala questo fatto e l'ora in cui la coda diventerà nuovamente disponibile. Quindi controlla il processo e, se non è disponibile, indica l'intervallo di tempo successivo quando è in grado di stampare. Infine, il metodo segnala la prima volta che il processo è in grado di stampare. Questo è il successivo di due volte.  
  
- Ora di disponibilità successiva della coda di stampa.  
  
- Ora successiva disponibile per il processo di stampa.  
  
 Quando si segnalano ora del giorno <xref:System.DateTime.ToShortTimeString%2A> , viene chiamato anche il metodo poiché questo metodo evita gli anni, i mesi e i giorni dall'output. Non è possibile limitare la disponibilità di una coda di stampa o di un processo di stampa a determinati anni, mesi o giorni.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 I due overload del metodo **ReportAvailabilityAtThisTime** sono identici, ad eccezione del tipo passato, quindi solo la <xref:System.Printing.PrintQueue> versione è riportata di seguito.  
  
> [!NOTE]
> Il fatto che i metodi siano identici, ad eccezione del tipo, genera la domanda sul motivo per cui l'esempio non crea un metodo generico **\<ReportAvailabilityAtThisTime T >** . Il motivo è che un metodo di questo tipo deve essere limitato a una classe con le proprietà **StartTimeOfDay** e **UntilTimeOfDay** chiamate dal metodo, ma un metodo generico può essere limitato solo a una singola classe e l'unica classe comune a entrambi e nell'albero di ereditarietà è <xref:System.Printing.PrintSystemObject> che non dispone di tali proprietà. <xref:System.Printing.PrintSystemJobInfo> <xref:System.Printing.PrintQueue>  
  
 Il metodo **ReportAvailabilityAtThisTime** (presentato nell'esempio di codice riportato di seguito) inizia con <xref:System.Boolean> l'inizializzazione `true`di una variabile Sentinel in. Se la coda non è `false`disponibile, verrà reimpostata su.  
  
 Successivamente, il metodo verifica se i tempi di inizio e di fine "fino a" sono identici. In caso affermativo, la coda è sempre disponibile, quindi il metodo `true`restituisce.  
  
 Se la coda non è sempre disponibile, il metodo usa la proprietà statica <xref:System.DateTime.UtcNow%2A> per ottenere l'ora corrente <xref:System.DateTime> come oggetto. Non è necessaria l'ora locale perché le <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> proprietà e <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> si trovano in ora UTC.  
  
 Tuttavia, queste due proprietà non <xref:System.DateTime> sono oggetti. Sono <xref:System.Int32>espresse l'ora come numero di minuti-dopo-UTC-mezzanotte. Quindi, dobbiamo convertire l' <xref:System.DateTime> oggetto in minuti, dopo la mezzanotte. Al termine, il metodo controlla semplicemente se "Now" è compreso tra l'inizio della coda e il valore "until", imposta la sentinella su false se "Now" non è compresa tra le due volte e restituisce Sentinel.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 Il metodo **TimeConverter. ConvertToLocalHumanReadableTime** (presentato nell'esempio di codice seguente) non usa metodi introdotti con Microsoft .NET Framework, quindi la discussione è breve. Il metodo dispone di un'attività di conversione doppia: deve prendere un numero intero che esprime minuti-dopo-mezzanotte e convertirlo in un tempo leggibile ed è necessario convertirlo nell'ora locale. Questa operazione viene eseguita creando innanzitutto un <xref:System.DateTime> oggetto impostato sulla mezzanotte UTC, quindi viene utilizzato il <xref:System.DateTime.AddMinutes%2A> metodo per aggiungere i minuti passati al metodo. Viene restituito un nuovo <xref:System.DateTime> oggetto che esprime l'ora originale passata al metodo. Il <xref:System.DateTime.ToLocalTime%2A> metodo converte quindi questo oggetto nell'ora locale.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.DateTime>
- <xref:System.Printing.PrintSystemJobInfo>
- <xref:System.Printing.PrintQueue>
- [Documenti in WPF](documents-in-wpf.md)
- [Panoramica della stampa](printing-overview.md)
