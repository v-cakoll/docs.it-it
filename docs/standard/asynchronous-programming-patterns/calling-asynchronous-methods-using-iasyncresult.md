---
title: Chiamata di metodi asincroni tramite IAsyncResult
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ab98973fadf1893b4954fd19f679fe0ff690539d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a>Chiamata di metodi asincroni tramite IAsyncResult
I tipi nelle librerie di classi di .NET Framework e di terze parti possono fornire metodi che consentono di continuare a eseguire un'applicazione durante l'esecuzione di operazioni asincrone in thread diversi dal thread dell'applicazione principale. Le sezioni seguenti descrivono e forniscono esempi di codice che illustrano i diversi modi in cui è possibile chiamare metodi asincroni che usano lo schema progettuale <xref:System.IAsyncResult>.  
  
-   [Blocco dell'esecuzione dell'applicazione terminando un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
-   [Blocco dell'esecuzione dell'applicazione tramite AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
-   [Esecuzione del polling dello stato di un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
-   [Uso di un delegato AsyncCallback per terminare un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)  
 [Panoramica sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
