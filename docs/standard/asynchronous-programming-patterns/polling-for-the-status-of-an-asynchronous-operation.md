---
title: Esecuzione del polling dello stato di un'operazione asincrona
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
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET Framework], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1f7f74a8b38c06f6a042d55c0def76ddfc5da77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a>Esecuzione del polling dello stato di un'operazione asincrona
Le applicazioni che è possano eseguire altre attività in attesa dei risultati di un'operazione asincrona non devono bloccarsi in attesa fino al completamento dell'operazione. Per continuare l'esecuzione di istruzioni durante l'attesa di completamento di un'operazione asincrona, utilizzare una delle opzioni seguenti:  
  
-   Utilizzare il <xref:System.IAsyncResult.IsCompleted%2A> proprietà del <xref:System.IAsyncResult> restituito tramite l'operazione asincrona **iniziare** *OperationName* metodo per determinare se l'operazione è stata completata. Questo approccio è noto come polling e viene illustrato in questo argomento.  
  
-   Utilizzare un <xref:System.AsyncCallback> delegato per elaborare i risultati dell'operazione asincrona in un thread separato. Per un esempio che illustra questo approccio, vedere [tramite un delegato AsyncCallback per terminare un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come utilizzare metodi asincroni nel <xref:System.Net.Dns> classe per recuperare le informazioni di sistema di nome di dominio per un computer specificato dall'utente. In questo esempio viene avviata l'operazione asincrona e vengono quindi stampati punti (".") nella console fino al completamento dell'operazione. Si noti che **null** (**nulla** in Visual Basic) viene passato il <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.AsyncCallback> e <xref:System.Object> parametri poiché questi argomenti non sono necessari quando si utilizza questo approccio.  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a>Vedere anche  
 [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi)  
 [Panoramica sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
