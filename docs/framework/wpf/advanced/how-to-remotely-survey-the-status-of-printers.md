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
ms.openlocfilehash: 4140152079b93e3c0a3d5fcda0e1b2c6f9fb89a4
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859856"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a>Procedura: Sorvegliare da remoto lo stato delle stampanti
In qualsiasi momento in aziende di medie e grandi dimensioni potrebbero essere presenti più stampanti non funzionanti a causa di fogli bloccati o carta esaurita o un'altra situazione problematica. Il set completo di proprietà della stampante esposto nell'API di Microsoft .NET Framework forniscono un mezzo per l'esecuzione di una rapida verifica dello stato delle stampanti.  
  
## <a name="example"></a>Esempio  
 Di seguito sono indicati i passaggi principali per la creazione di questo tipo di utilità.  
  
1. Ottenere un elenco di tutti i server di stampa.  
  
2. Scorrere i server per eseguire una query sulle code di stampa.  
  
3. In ogni passaggio del ciclo del server, scorrere tutte le code del server e leggere tutte le proprietà che potrebbero indicare che la coda attualmente non funziona.  
  
 Il codice seguente è una serie di frammenti di codice. Per semplicità, in questo esempio si presuppone che esista un elenco delimitato da CRLF di server di stampa. La variabile `fileOfPrintServers` è un <xref:System.IO.StreamReader> oggetto per questo file. Poiché ogni nome del server è su una riga, tutte le chiamate di <xref:System.IO.StreamReader.ReadLine%2A> Ottiene il nome del server successivo e sposta il <xref:System.IO.StreamReader>del cursore all'inizio della riga successiva.  
  
 All'interno del ciclo esterno, il codice crea un <xref:System.Printing.PrintServer> dell'oggetto per il server di stampa più recente e specifica che l'applicazione deve avere diritti amministrativi per il server.  
  
> [!NOTE]
>  Se sono presenti un numero elevato di server, è possibile migliorare le prestazioni usando il <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> che inizializzano solo le proprietà si intende necessario.  
  
 L'esempio Usa quindi <xref:System.Printing.PrintServer.GetPrintQueues%2A> per creare una raccolta di tutti i server del mette in coda e inizia a eseguire un ciclo. Il ciclo interno include una struttura ramificata corrispondente ai due metodi di verifica dello stato della stampante:  
  
- È possibile leggere i flag del <xref:System.Printing.PrintQueue.QueueStatus%2A> proprietà che è di tipo <xref:System.Printing.PrintQueueStatus>.  
  
- È possibile leggere tutte le proprietà rilevanti, ad esempio <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, e <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.  
  
 In questo esempio illustra entrambi i metodi, in modo che l'utente è stato chiesto di specificare il metodo da usare in precedenza e ha risposto con "y" se voleva usare i flag del <xref:System.Printing.PrintQueue.QueueStatus%2A> proprietà. Per i dettagli dei due metodi, vedere di seguito.  
  
 Infine, i risultati vengono presentati all'utente.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 Per controllare lo stato delle stampanti usando i flag del <xref:System.Printing.PrintQueue.QueueStatus%2A> proprietà, esaminare ogni flag pertinente per verificare se è impostato. Il metodo standard per verificare se un bit è impostato in un set di flag di bit consiste nell'eseguire un'operazione di AND logico con il set di flag come uno degli operandi e il flag stesso come altro operando. Poiché il flag stesso ha un solo bit impostato, il risultato dell'AND logico è che, al massimo, è impostato quello stesso bit. Per verificare se lo è o meno, confrontare il risultato dell’AND logico con il flag stesso. Per altre informazioni, vedere <xref:System.Printing.PrintQueueStatus>, il [& operatore (C# riferimento)](~/docs/csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-), e <xref:System.FlagsAttribute>.  
  
 Per ogni attributo il cui bit è impostato, il codice aggiunge un avviso al report finale che verrà presentato all'utente. (Il metodo **ReportAvailabilityAtThisTime** che viene chiamato alla fine del codice è illustrato di seguito.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 Per controllare lo stato delle stampanti usando tutte le proprietà, basta leggere tutte le proprietà e aggiungere una nota alla relazione finale che sarà presentata all'utente se la proprietà è `true`. (Il metodo **ReportAvailabilityAtThisTime** che viene chiamato alla fine del codice è illustrato di seguito.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 Il metodo **ReportAvailabilityAtThisTime** è stato creato nel caso in cui sia necessario determinare se la coda è disponibile in quel momento preciso del giorno.  
  
 Il metodo non eseguirà alcuna operazione se il <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> e <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> proprietà sono uguali; perché in tal caso la stampante è disponibile in qualsiasi momento. Se sono diversi, il metodo ottiene l'ora corrente, che deve quindi essere convertita nel numero totale di minuti trascorsi dalla mezzanotte, poiché il <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> e <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> le proprietà sono <xref:System.Int32>che rappresentano i minuti dopo la mezzanotte, non <xref:System.DateTime> oggetti. Infine, il metodo controlla se l'ora corrente è compresa tra l'inizio e il lasso di tempo "fino a".  
  
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
- [& Operatore (C# riferimento)](~/docs/csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [Documenti in WPF](documents-in-wpf.md)
- [Panoramica della stampa](printing-overview.md)
