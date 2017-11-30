---
title: Blocco dell'esecuzione dell'applicazione tramite AsyncWaitHandle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- blocks, asynchronous operations
- ending asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming, blocking applications
- stopping asynchronous operations
- blocking application execution
ms.assetid: 3e32daf2-8161-4e8f-addd-9fd9ff101b03
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2660b3cbf7e8ee43a22edbfb66a4262684983b87
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a>Blocco dell'esecuzione dell'applicazione tramite AsyncWaitHandle
Le applicazioni che non possono continuare a eseguire altre attività in attesa dei risultati di un'operazione asincrona, devono restare bloccati fino al completamento dell'operazione. Bloccare il thread principale dell'applicazione durante l'attesa di completamento di un'operazione asincrona, utilizzare una delle opzioni seguenti:  
  
-   Utilizzare il <xref:System.IAsyncResult.AsyncWaitHandle%2A> proprietà del <xref:System.IAsyncResult> restituito tramite l'operazione asincrona **iniziare** *OperationName* metodo. Questo approccio viene illustrato in questo argomento.  
  
-   Chiamare l'operazione asincrona **fine** *OperationName* metodo. Per un esempio che illustra questo approccio, vedere [il blocco di esecuzione dell'applicazione terminando un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
 Le applicazioni che utilizzano uno o più <xref:System.Threading.WaitHandle> verranno chiamato in genere gli oggetti di blocco fino al completamento di un'operazione asincrona di **iniziare** *OperationName* (metodo), eseguire le operazioni che possono essere eseguite senza i risultati dell'operazione e blocco finché l'operazione di operazioni asincrone completa. Un'applicazione può essere bloccata in una singola operazione chiamando uno del <xref:System.Threading.WaitHandle.WaitOne%2A> metodi usando il <xref:System.IAsyncResult.AsyncWaitHandle%2A>. Per il blocco durante l'attesa di un set di operazioni asincrone per completare, archiviare associato <xref:System.IAsyncResult.AsyncWaitHandle%2A> oggetti in una matrice e chiamare uno del <xref:System.Threading.WaitHandle.WaitAll%2A> metodi. Per il blocco durante l'attesa per uno qualsiasi di un set di operazioni asincrone per completare, archiviare associato <xref:System.IAsyncResult.AsyncWaitHandle%2A> oggetti in una matrice e chiamare uno del <xref:System.Threading.WaitHandle.WaitAny%2A> metodi.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato l'utilizzo di metodi asincroni nella classe DNS per recuperare le informazioni di sistema di nome di dominio per un computer specificato dall'utente. Nell'esempio viene illustrato il blocco utilizzando la <xref:System.Threading.WaitHandle> associato all'operazione asincrona. Si noti che `null` (`Nothing` in Visual Basic) viene passato il <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` e `stateObject` parametri perché non sono necessarie quando si utilizza questo approccio.  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi)  
 [Panoramica sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
