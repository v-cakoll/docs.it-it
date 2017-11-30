---
title: Thread in primo piano e in background
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ad427fc2c1175c0d9b333aa418aea039f11a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="foreground-and-background-threads"></a>Thread in primo piano e in background
Un thread gestito è un thread in background o un thread in primo piano. Thread in background sono identiche a thread in foreground con un'unica eccezione: un thread in background non mantiene l'ambiente di esecuzione gestito. Una volta tutti i thread in primo piano sono stati interrotti in un processo gestito (in cui il file .exe è un assembly gestito), il sistema di tutti i thread in background e viene chiuso.  
  
> [!NOTE]
>  Quando il runtime interrompe un thread in background, perché si sta arrestando il processo, viene generata alcuna eccezione nel thread. Tuttavia, quando i thread vengono interrotti perché il <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> metodo scarica il dominio dell'applicazione, un <xref:System.Threading.ThreadAbortException> viene generata nel thread di sfondo e primo piano.  
  
 Utilizzare il <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> proprietà per determinare se un thread è uno sfondo o un thread in primo piano o per modificare il relativo stato. Un thread può essere cambiato in un thread in background in qualsiasi momento impostando il relativo <xref:System.Threading.Thread.IsBackground%2A> proprietà `true`.  
  
> [!IMPORTANT]
>  Lo stato di primo piano o di sfondo di un thread non incidono sul risultato di un'eccezione non gestita nel thread. In .NET Framework versione 2.0, un'eccezione non gestita in primo piano o in background thread comporta la terminazione dell'applicazione. Vedere [eccezioni in thread gestiti](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
 Thread che appartengono al pool di thread gestiti (ovvero, i thread la cui <xref:System.Threading.Thread.IsThreadPoolThread%2A> proprietà `true`) sono thread in background. Tutti i thread che accedono all'ambiente di esecuzione gestita dal codice non gestito sono contrassegnati come thread in background. Tutti i thread generati creando e avviando un nuovo <xref:System.Threading.Thread> oggetto sono thread per impostazione predefinita in primo piano.  
  
 Se si utilizza un thread per monitorare un'attività, ad esempio una connessione socket, impostare il relativo <xref:System.Threading.Thread.IsBackground%2A> proprietà `true` in modo che il thread non impedisce l'interruzione del processo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadAbortException>
