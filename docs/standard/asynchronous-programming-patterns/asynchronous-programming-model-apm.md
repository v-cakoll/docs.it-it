---
title: Modello di programmazione asincrona (APM)
description: Informazioni sul modello di programmazione asincrona (APM) in .NET. Scopri come iniziare e terminare un'operazione asincrona.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- starting asynchronous operations
- beginning asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming
- stopping asynchronous operations
- asynchronous programming, beginning operations
ms.assetid: c9b3501e-6bc6-40f9-8efd-4b6d9e39ccf0
ms.openlocfilehash: 5ab5d15d24aac80ef4a31c039f7af9dacce4a8d8
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769184"
---
# <a name="asynchronous-programming-model-apm"></a>Modello di programmazione asincrona (APM)
Un'operazione asincrona in cui viene usato il modello di progettazione dell'oggetto <xref:System.IAsyncResult> viene implementata come due metodi denominati `BeginOperationName` e `EndOperationName` tramite cui viene rispettivamente avviata e terminata l'operazione asincrona *NomeOperazione*. La classe <xref:System.IO.FileStream> fornisce ad esempio i metodi <xref:System.IO.FileStream.BeginRead%2A> e <xref:System.IO.FileStream.EndRead%2A> per la lettura asincrona dei byte da un file. Tali metodi implementano la versione asincrona del metodo <xref:System.IO.FileStream.Read%2A> .  
  
> [!NOTE]
> A partire da .NET Framework 4, Task Parallel Library fornisce un nuovo modello di programmazione asincrona e parallela. Per altre informazioni, vedere [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) e [modello asincrono basato su attività (TAP)](task-based-asynchronous-pattern-tap.md).  
  
 Dopo aver chiamato il metodo `BeginOperationName`, l'app può continuare a eseguire le istruzioni nel thread chiamante mentre l'operazione asincrona viene eseguita in un altro thread. Per ogni chiamata a `BeginOperationName`, l'app deve chiamare anche il metodo `EndOperationName` per ottenere i risultati dell'operazione.  
  
## <a name="beginning-an-asynchronous-operation"></a>Avvio di un'operazione asincrona  
 Il metodo `BeginOperationName` avvia l'operazione asincrona *NomeOperazione* e restituisce un oggetto che implementa l'interfaccia <xref:System.IAsyncResult>. Gli oggetti<xref:System.IAsyncResult> archiviano le informazioni sulle operazioni asincrone. La tabella seguente illustra le informazioni relative a un'operazione asincrona.  
  
|Membro|Descrizione|  
|------------|-----------------|  
|<xref:System.IAsyncResult.AsyncState%2A>|Oggetto facoltativo specifico dell'applicazione che contiene informazioni sull'operazione asincrona.|  
|<xref:System.IAsyncResult.AsyncWaitHandle%2A>|Oggetto <xref:System.Threading.WaitHandle> che può essere usato per bloccare l'esecuzione dell'applicazione fino al completamento dell'operazione asincrona.|  
|<xref:System.IAsyncResult.CompletedSynchronously%2A>|Valore che indica l'eventuale completamento dell'operazione asincrona nel thread usato per chiamare il metodo `BeginOperationName` anziché in un thread <xref:System.Threading.ThreadPool> separato.|  
|<xref:System.IAsyncResult.IsCompleted%2A>|Valore che indica l'eventuale completamento dell'operazione asincrona.|  
  
 In un metodo `BeginOperationName` vengono accettati tutti i parametri dichiarati nella firma della versione sincrona del metodo passati per valore o riferimento. Nella firma del metodo `BeginOperationName` non sono inclusi parametri out. Il metodo `BeginOperationName` include invece due parametri aggiuntivi. Il primo dei quali definisce un delegato <xref:System.AsyncCallback> che fa riferimento a un metodo chiamato al completamento dell'operazione asincrona. Il chiamante può specificare `null` (`Nothing` in Visual Basic) se non vuole richiamare un metodo al termine dell'operazione. Il secondo parametro aggiuntivo è un oggetto definito dall'utente che può essere usato per passare informazioni sullo stato specifiche dell'applicazione al metodo richiamato al completamento dell'operazione asincrona. Se in un metodo `BeginOperationName` sono accettati altri parametri specifici dell'operazione, ad esempio una matrice di byte per l'archiviazione dei byte letti da un file, l'oggetto <xref:System.AsyncCallback> e l'oggetto stato dell'applicazione saranno gli ultimi parametri nella firma del metodo `BeginOperationName`.  
  
 Il metodo `BeginOperationName` restituisce immediatamente il controllo al thread chiamante. Se il metodo `BeginOperationName` genera eccezioni, ciò avviene prima dell'avvio dell'operazione asincrona e il metodo `BeginOperationName`di callback non viene richiamato.  
  
## <a name="ending-an-asynchronous-operation"></a>Fine di un'operazione asincrona  
 Il metodo `EndOperationName` termina l'operazione asincrona *NomeOperazione*. Il valore restituito dal metodo `EndOperationName` è dello stesso tipo restituito dalla controparte sincrona ed è specifico dell'operazione asincrona. Il metodo <xref:System.IO.FileStream.EndRead%2A> restituisce ad esempio il numero di byte letti da un oggetto <xref:System.IO.FileStream> mentre il metodo <xref:System.Net.Dns.EndGetHostByName%2A> restituisce un oggetto <xref:System.Net.IPHostEntry> contenente le informazioni relative a un computer host. Il metodo `EndOperationName` accetta tutti i parametri out o ref dichiarati nella firma della versione sincrona del metodo. Oltre ai parametri provenienti dal metodo sincrono, nel metodo `EndOperationName` è incluso anche un parametro <xref:System.IAsyncResult>. I chiamanti devono passare l'istanza restituita dalla chiamata corrispondente al metodo `BeginOperationName`.  
  
 Se l'operazione asincrona rappresentata dall'oggetto <xref:System.IAsyncResult> non è stata completata quando viene chiamato il metodo `EndOperationName`, `EndOperationName`quest'ultimo blocca il thread chiamante fino al completamento dell'operazione. Le eccezioni generate dall'operazione asincrona vengono generate dal metodo `EndOperationName`. Non è definito l'effetto della chiamata ripetuta del metodo `EndOperationName` con lo stesso oggetto <xref:System.IAsyncResult>, come anche della chiamata del metodo `EndOperationName` con un oggetto <xref:System.IAsyncResult> non restituito dal metodo Begin correlato.  
  
> [!NOTE]
> In questi due scenari non definiti ai responsabili dell'implementazione è consigliata la generazione di <xref:System.InvalidOperationException>.  
  
> [!NOTE]
> I responsabili dell'implementazione di questo schema progettuale devono notificare al chiamante il completamento dell'operazione asincrona impostando <xref:System.IAsyncResult.IsCompleted%2A> su true, chiamando il metodo di callback asincrono, se specificato, e segnalando l'oggetto <xref:System.IAsyncResult.AsyncWaitHandle%2A>.  
  
 Gli sviluppatori di applicazioni dispongono di diverse scelte di progettazione per accedere ai risultati dell'operazione asincrona. La scelta adeguata dipende dall'eventuale presenza nell'applicazione di istruzioni che possono essere eseguite durante il completamento dell'operazione. Se l'applicazione non consente di eseguire altre attività fino alla ricezione dei risultati dell'operazione asincrona, deve essere bloccata fino a quel momento. A tale scopo, sono disponibili i due approcci illustrati di seguito:  
  
- Chiamare il metodo `EndOperationName` dal thread principale dell'applicazione, bloccando l'esecuzione dell'applicazione fino al completamento dell'operazione. Per un esempio relativo all'uso di questa tecnica, vedere [Blocco dell'esecuzione dell'applicazione terminando un'operazione asincrona](blocking-application-execution-by-ending-an-async-operation.md).  
  
- Usare <xref:System.IAsyncResult.AsyncWaitHandle%2A> per bloccare l'esecuzione dell'applicazione fino al completamento di una o più operazioni. Per un esempio relativo all'uso di questa tecnica, vedere [Blocking Application Execution Using an AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md).  
  
 Per le applicazioni che non è necessario bloccare durante il completamento dell'operazione asincrona, è possibile usare uno degli approcci seguenti:  
  
- Eseguire il polling dello stato di completamento dell'operazione verificando periodicamente la proprietà <xref:System.IAsyncResult.IsCompleted%2A> e chiamando il metodo `EndOperationName` al completamento dell'operazione. Per un esempio relativo all'uso di questa tecnica, vedere [Polling for the Status of an Asynchronous Operation](polling-for-the-status-of-an-asynchronous-operation.md).  
  
- Usare un delegato <xref:System.AsyncCallback> per specificare il metodo da richiamare quando l'operazione viene completata. Per un esempio relativo all'uso di questa tecnica, vedere [Using an AsyncCallback Delegate to End an Asynchronous Operation](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="see-also"></a>Vedere anche

- [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)
- [Chiamata di metodi sincroni in modalità asincrona](calling-synchronous-methods-asynchronously.md)
- [Utilizzo di un oggetto di stato e di un delegato AsyncCallback](using-an-asynccallback-delegate-and-state-object.md)
