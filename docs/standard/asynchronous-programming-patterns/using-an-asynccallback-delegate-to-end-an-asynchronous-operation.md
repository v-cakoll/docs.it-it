---
title: Utilizzo di un delegato AsyncCallback per terminare un'operazione asincrona
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
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bbe170588776daa97fec4c736d4b1bdd871de518
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a>Utilizzo di un delegato AsyncCallback per terminare un'operazione asincrona
Le applicazioni che è possano eseguire altre attività in attesa dei risultati di un'operazione asincrona non devono bloccarsi in attesa fino al completamento dell'operazione. Per continuare l'esecuzione di istruzioni durante l'attesa di completamento di un'operazione asincrona, utilizzare una delle opzioni seguenti:  
  
-   Utilizzare un <xref:System.AsyncCallback> delegato per elaborare i risultati dell'operazione asincrona in un thread separato. Questo approccio viene illustrato in questo argomento.  
  
-   Utilizzare il <xref:System.IAsyncResult.IsCompleted%2A> proprietà del <xref:System.IAsyncResult> restituito tramite l'operazione asincrona **iniziare** *OperationName* metodo per determinare se l'operazione è stata completata. Per un esempio che illustra questo approccio, vedere [il Polling dello stato dell'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come utilizzare metodi asincroni nel <xref:System.Net.Dns> classe per recuperare le informazioni di sistema DNS (Domain Name) per i computer specificati dall'utente. Questo esempio viene creato un <xref:System.AsyncCallback> delegato che fa riferimento il `ProcessDnsInformation` metodo. Questo metodo viene chiamato una volta per ogni richiesta asincrona per le informazioni DNS.  
  
 Si noti che l'host specificato dall'utente viene passato per il <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Object> parametro. Per un esempio che illustra la definizione e utilizzo di un oggetto di stato più complesso, vedere [tramite un delegato AsyncCallback e un oggetto di stato](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a>Vedere anche  
 [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi)  
 [Panoramica sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [Chiamata di metodi asincroni tramite IAsyncResult](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)  
 [Uso di un oggetto di stato e di un delegato AsyncCallback](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
