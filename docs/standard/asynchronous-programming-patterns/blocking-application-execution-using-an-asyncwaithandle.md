---
title: Blocco dell'esecuzione dell'applicazione tramite AsyncWaitHandle
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 16b5a297c13cd9096548ed489e4994b72a48da67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121432"
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a>Blocco dell'esecuzione dell'applicazione tramite AsyncWaitHandle
Le applicazioni che non possono continuare a eseguire altre attività in attesa dei risultati di un'operazione asincrona devono restare bloccati fino al completamento dell'operazione. Usare una delle opzioni seguenti per bloccare il thread principale dell'applicazione in attesa del completamento di un'operazione asincrona:  
  
- Usare la proprietà <xref:System.IAsyncResult.AsyncWaitHandle%2A> dell'interfaccia <xref:System.IAsyncResult> restituita dal metodo **Begin**_OperationName_ dell'operazione asincrona. Questo metodo viene dimostrato in questo argomento.  
  
- Chiamare il metodo **End**_OperationName_ dell'operazione asincrona. Per un esempio relativo all'uso di questo approccio, vedere [Blocco dell'esecuzione dell'applicazione terminando un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
 Le applicazioni che usano uno o più oggetti <xref:System.Threading.WaitHandle> per il blocco fino al completamento di un'operazione asincrona chiameranno in genere il metodo **Begin**_OperationName_, effettueranno qualsiasi attività eseguibile senza i risultati dell'operazione e quindi verranno bloccate fino al completamento delle operazioni asincrone. Un'applicazione può essere bloccata su una singola operazione chiamando uno dei metodi <xref:System.Threading.WaitHandle.WaitOne%2A> con la proprietà <xref:System.IAsyncResult.AsyncWaitHandle%2A>. Per applicare il blocco in attesa del completamento di un set di operazioni asincrone, archiviare gli oggetti <xref:System.IAsyncResult.AsyncWaitHandle%2A> associati in una matrice e chiamare uno dei metodi <xref:System.Threading.WaitHandle.WaitAll%2A>. Per applicare il blocco in attesa del completamento di un'operazione asincrona di un set, archiviare gli oggetti <xref:System.IAsyncResult.AsyncWaitHandle%2A> associati in una matrice e chiamare uno dei metodi <xref:System.Threading.WaitHandle.WaitAny%2A>.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente illustra l'uso dei metodi asincroni nella classe DNS per recuperare le informazioni di Domain Name System per un computer specificato dall'utente. L'esempio illustra il blocco tramite la classe <xref:System.Threading.WaitHandle> associata all'operazione asincrona. Si noti che viene passato `null` (`Nothing` in Visual Basic) per i parametri `requestCallback` e `stateObject` di <xref:System.Net.Dns.BeginGetHostByName%2A> perché non sono necessari quando si usa questo approccio.  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)
- [Cenni preliminari sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
