---
title: Blocco dell'esecuzione dell'applicazione terminando un'operazione asincrona
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
dev_langs:
- csharp
- vb
ms.openlocfilehash: ccca6e1e4f6b5cdf098018b59426fb2262e2b346
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a>Blocco dell'esecuzione dell'applicazione terminando un'operazione asincrona
Le applicazioni che non possono continuare a eseguire altre attività in attesa dei risultati di un'operazione asincrona, devono restare bloccati fino al completamento dell'operazione. Bloccare il thread principale dell'applicazione durante l'attesa di completamento di un'operazione asincrona, utilizzare una delle opzioni seguenti:  
  
-   Chiamare le operazioni asincrone **fine** *OperationName* metodo. Questo approccio viene illustrato in questo argomento.  
  
-   Utilizzare il <xref:System.IAsyncResult.AsyncWaitHandle%2A> proprietà del <xref:System.IAsyncResult> restituito tramite l'operazione asincrona **iniziare** *OperationName* metodo. Per un esempio che illustra questo approccio, vedere [il blocco di esecuzione dell'applicazione tramite AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
 Le applicazioni che utilizzano il **fine** *OperationName* verrà in genere chiamata al metodo di blocco fino al completamento di un'operazione asincrona di **iniziare**  *OperationName* (metodo), eseguire le operazioni che possono essere eseguita senza i risultati dell'operazione e quindi chiamano **fine** *OperationName*.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come utilizzare metodi asincroni nel <xref:System.Net.Dns> classe per recuperare le informazioni di sistema di nome di dominio per un computer specificato dall'utente. Si noti che `null` (`Nothing` in Visual Basic) viene passato il <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` e `stateObject` parametri poiché questi argomenti non sono necessari quando si utilizza questo approccio.  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi)  
 [Panoramica sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
