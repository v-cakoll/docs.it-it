---
title: 'Procedura: Sorvegliare da remoto lo stato delle stampanti'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- surveying printer status remotely [WPF]
- printer status [WPF], surveying remotely
- remotely surveying printer status [WPF]
- status [WPF], printers [WPF], surveying remotely
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
ms.openlocfilehash: 0a7756684d5a133fa9cb014f109d14e413223ea9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945231"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a>Procedura: Sorvegliare da remoto lo stato delle stampanti
In qualsiasi momento in aziende di medie e grandi dimensioni potrebbero essere presenti più stampanti non funzionanti a causa di fogli bloccati o carta esaurita o un'altra situazione problematica. Il set completo di proprietà della stampante esposte nelle API di Microsoft .NET Framework fornisce un mezzo per eseguire un rapido sondaggio degli Stati delle stampanti.  
  
## <a name="example"></a>Esempio  
 Di seguito sono indicati i passaggi principali per la creazione di questo tipo di utilità.  
  
1. Ottenere un elenco di tutti i server di stampa.  
  
2. Scorrere i server per eseguire una query sulle code di stampa.  
  
3. In ogni passaggio del ciclo del server, scorrere tutte le code del server e leggere tutte le proprietà che potrebbero indicare che la coda attualmente non funziona.  
  
 Il codice seguente è una serie di frammenti di codice. Per semplicità, in questo esempio si presuppone che esista un elenco delimitato da CRLF di server di stampa. La variabile `fileOfPrintServers` è un <xref:System.IO.StreamReader> oggetto per il file. Poiché ogni nome di server si trova su una riga a se stante <xref:System.IO.StreamReader.ReadLine%2A> , qualsiasi chiamata di ottiene il nome del server successivo <xref:System.IO.StreamReader>e sposta il cursore all'inizio della riga successiva.  
  
 All'interno del ciclo esterno, il codice crea <xref:System.Printing.PrintServer> un oggetto per il server di stampa più recente e specifica che l'applicazione deve disporre di diritti amministrativi per il server.  
  
> [!NOTE]
> Se sono presenti numerosi server, è possibile migliorare le prestazioni usando i <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> costruttori che inizializzano solo le proprietà necessarie.  
  
 Nell'esempio viene quindi <xref:System.Printing.PrintServer.GetPrintQueues%2A> usato per creare una raccolta di tutte le code del server e iniziare a scorrerle. Il ciclo interno include una struttura ramificata corrispondente ai due metodi di verifica dello stato della stampante:  
  
- È possibile leggere i flag della <xref:System.Printing.PrintQueue.QueueStatus%2A> proprietà che è di tipo. <xref:System.Printing.PrintQueueStatus>  
  
- È possibile leggere tutte le proprietà rilevanti <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, ad esempio, e. <xref:System.Printing.PrintQueue.IsPaperJammed%2A>  
  
 Questo esempio illustra entrambi i metodi, quindi all'utente è stato chiesto in precedenza come metodo da usare e ha risposto con "y" se volesse usare i flag della <xref:System.Printing.PrintQueue.QueueStatus%2A> proprietà. Per i dettagli dei due metodi, vedere di seguito.  
  
 Infine, i risultati vengono presentati all'utente.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 Per controllare lo stato della stampante usando i flag <xref:System.Printing.PrintQueue.QueueStatus%2A> della proprietà, controllare ogni flag pertinente per verificare se è impostato. Il metodo standard per verificare se un bit è impostato in un set di flag di bit consiste nell'eseguire un'operazione di AND logico con il set di flag come uno degli operandi e il flag stesso come altro operando. Poiché il flag stesso ha un solo bit impostato, il risultato dell'AND logico è che, al massimo, è impostato quello stesso bit. Per verificare se lo è o meno, confrontare il risultato dell’AND logico con il flag stesso. Per ulteriori informazioni, vedere <xref:System.Printing.PrintQueueStatus>l' [operatore & (C# riferimento)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)e. <xref:System.FlagsAttribute>  
  
 Per ogni attributo il cui bit è impostato, il codice aggiunge un avviso al report finale che verrà presentato all'utente. (Il metodo **ReportAvailabilityAtThisTime** che viene chiamato alla fine del codice è illustrato di seguito.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 Per controllare lo stato delle stampanti usando tutte le proprietà, basta leggere tutte le proprietà e aggiungere una nota alla relazione finale che sarà presentata all'utente se la proprietà è `true`. (Il metodo **ReportAvailabilityAtThisTime** che viene chiamato alla fine del codice è illustrato di seguito.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 Il metodo **ReportAvailabilityAtThisTime** è stato creato nel caso in cui sia necessario determinare se la coda è disponibile in quel momento preciso del giorno.  
  
 Il metodo non eseguirà alcuna operazione <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> se <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> le proprietà e sono uguali; in tal caso, la stampante è sempre disponibile. Se sono diversi, il metodo ottiene l'ora corrente che deve quindi essere convertita in minuti totali dopo la mezzanotte perché le <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> proprietà <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> e sono <xref:System.Int32>che rappresentano i minuti, dopo la mezzanotte, <xref:System.DateTime> non oggetti. Infine, il metodo controlla se l'ora corrente è compresa tra l'inizio e il lasso di tempo "fino a".  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>
- <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>
- <xref:System.DateTime>
- <xref:System.Printing.PrintQueueStatus>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- [Operatore & (C# riferimento)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [Documenti in WPF](documents-in-wpf.md)
- [Panoramica della stampa](printing-overview.md)
