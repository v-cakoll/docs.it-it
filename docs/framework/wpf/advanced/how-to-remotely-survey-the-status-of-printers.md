---
title: 'Procedura: verificare lo stato delle stampanti da postazione remota'
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
ms.openlocfilehash: 859ccb703c6c54c66d6ea7b433c67d156627e25b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187032"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a>Procedura: verificare lo stato delle stampanti da postazione remota
In qualsiasi momento in aziende di medie e grandi dimensioni potrebbero essere presenti più stampanti non funzionanti a causa di fogli bloccati o carta esaurita o un'altra situazione problematica. Il ricco set di proprietà della stampante esposte nelle API di Microsoft .NET Framework fornisce un mezzo per eseguire un rapido rilevamento degli stati delle stampanti.  
  
## <a name="example"></a>Esempio  
 Di seguito sono indicati i passaggi principali per la creazione di questo tipo di utilità.  
  
1. Ottenere un elenco di tutti i server di stampa.  
  
2. Riprodurre il ciclo dei server per eseguire una query sulle code di stampa.  
  
3. In ogni passaggio del ciclo del server, scorrere tutte le code del server e leggere tutte le proprietà che potrebbero indicare che la coda attualmente non funziona.  
  
 Il codice seguente è una serie di frammenti di codice. Per semplicità, in questo esempio si presuppone che esista un elenco delimitato da CRLF di server di stampa. La `fileOfPrintServers` variabile <xref:System.IO.StreamReader> è un oggetto per questo file. Poiché il nome di ogni server <xref:System.IO.StreamReader.ReadLine%2A> si trova sulla propria riga, <xref:System.IO.StreamReader>ogni chiamata di ottiene il nome del server successivo e sposta il cursore all'inizio della riga successiva.  
  
 All'interno del ciclo esterno, il codice crea un <xref:System.Printing.PrintServer> oggetto per il server di stampa più recente e specifica che l'applicazione deve disporre di diritti amministrativi per il server.  
  
> [!NOTE]
> Se sono presenti molti server, è possibile <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> migliorare le prestazioni utilizzando i costruttori che inizializzano solo le proprietà necessarie.  
  
 Nell'esempio <xref:System.Printing.PrintServer.GetPrintQueues%2A> viene quindi utilizzato per creare una raccolta di tutte le code del server e inizia a scorrere in ciclo. Il ciclo interno include una struttura ramificata corrispondente ai due metodi di verifica dello stato della stampante:  
  
- È possibile leggere i <xref:System.Printing.PrintQueue.QueueStatus%2A> flag della <xref:System.Printing.PrintQueueStatus>proprietà che è di tipo .  
  
- È possibile leggere ogni <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>proprietà <xref:System.Printing.PrintQueue.IsPaperJammed%2A>rilevante, ad esempio , e .  
  
 In questo esempio vengono illustrati entrambi i metodi, pertanto all'utente è stato precedentemente richiesto quale <xref:System.Printing.PrintQueue.QueueStatus%2A> metodo utilizzare e ha risposto con "y" se desiderava utilizzare i flag della proprietà. Per i dettagli dei due metodi, vedere di seguito.  
  
 Infine, i risultati vengono presentati all'utente.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 Per controllare lo stato della <xref:System.Printing.PrintQueue.QueueStatus%2A> stampante utilizzando i flag della proprietà, controllare ogni flag pertinente per vedere se è impostato. Il metodo standard per verificare se un bit è impostato in un set di flag di bit consiste nell'eseguire un'operazione di AND logico con il set di flag come uno degli operandi e il flag stesso come altro operando. Poiché il flag stesso ha un solo bit impostato, il risultato dell'AND logico è che, al massimo, è impostato quello stesso bit. Per verificare se lo è o meno, confrontare il risultato dell’AND logico con il flag stesso. Per ulteriori informazioni, vedere <xref:System.Printing.PrintQueueStatus>, l'operatore& [(Riferimenti per C)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)e <xref:System.FlagsAttribute>.  
  
 Per ogni attributo il cui bit è impostato, il codice aggiunge un avviso al report finale che verrà presentato all'utente. (Il metodo **ReportAvailabilityAtThisTime** che viene chiamato alla fine del codice è illustrato di seguito.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 Per controllare lo stato delle stampanti usando tutte le proprietà, basta leggere tutte le proprietà e aggiungere una nota alla relazione finale che sarà presentata all'utente se la proprietà è `true`. (Il metodo **ReportAvailabilityAtThisTime** che viene chiamato alla fine del codice è illustrato di seguito.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 Il metodo **ReportAvailabilityAtThisTime** è stato creato nel caso in cui sia necessario determinare se la coda è disponibile in quel momento preciso del giorno.  
  
 Il metodo non eseguirà alcuna operazione se le <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> proprietà e <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> sono uguali; perché in tal caso la stampante è sempre disponibile. Se sono diversi, il metodo ottiene l'ora corrente che deve essere <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> convertita <xref:System.Int32>in minuti totali dopo la <xref:System.DateTime> mezzanotte perché le proprietà e sono s che rappresentano i minuti dopo la mezzanotte, non gli oggetti. Infine, il metodo controlla se l'ora corrente è compresa tra l'inizio e il lasso di tempo "fino a".  
  
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
- [Operatore& (Riferimenti per C](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [Documenti in WPF](documents-in-wpf.md)
- [Cenni preliminari sulla stampa](printing-overview.md)
