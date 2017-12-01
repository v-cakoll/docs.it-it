---
title: Eliminazione definitiva di thread
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
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a41dce5db707d0be49c283256de665d316e1a1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="destroying-threads"></a>Eliminazione definitiva di thread
Il <xref:System.Threading.Thread.Abort%2A> metodo viene utilizzato per interrompere un thread gestito in modo permanente. Quando si chiama <xref:System.Threading.Thread.Abort%2A>, common language runtime genera un <xref:System.Threading.ThreadAbortException> nel thread di destinazione, in grado di rilevare il thread di destinazione. Per altre informazioni, vedere <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Se è in esecuzione un thread non gestito il codice quando il relativo <xref:System.Threading.Thread.Abort%2A> metodo viene chiamato, il runtime contrassegna <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>. L'eccezione viene generata quando il thread viene restituito al codice gestito.  
  
 Quando un thread viene interrotto, non può essere riavviato.  
  
 Il <xref:System.Threading.Thread.Abort%2A> metodo non determina l'interruzione immediata, il thread perché il thread di destinazione può intercettare il <xref:System.Threading.ThreadAbortException> ed eseguire quantità arbitraria di codice in un `finally` blocco. È possibile chiamare <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> se è necessario attendere che il thread è stata terminata. <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>è una chiamata di blocco non termina finché il thread effettivamente ha interrotto l'esecuzione o è trascorso un intervallo di timeout facoltativo. Il thread interrotto può chiamare il <xref:System.Threading.Thread.ResetAbort%2A> metodo o eseguire un'elaborazione illimitata in una `finally` blocca, pertanto se non si specifica un timeout, il tempo di attesa non è garantita per terminare.  
  
 Thread in attesa su una chiamata al <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> metodo può essere interrotta da altri thread che chiamano <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.  
  
## <a name="handling-threadabortexception"></a>Gestione di ThreadAbortException  
 Se si prevede che il thread viene interrotta, come risultato della chiamata <xref:System.Threading.Thread.Abort%2A> dal proprio codice o in seguito a un dominio applicazione in cui viene eseguito il thread di scaricamento (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> utilizza <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> per interrompere i thread), il thread deve gestire il <xref:System.Threading.ThreadAbortException> ed eseguire un'eventuale elaborazione finale in un `finally` clausola, come illustrato nel codice seguente.  
  
```vb  
Try  
    ' Code that is executing when the thread is aborted.  
Catch ex As ThreadAbortException  
    ' Clean-up code can go here.  
    ' If there is no Finally clause, ThreadAbortException is  
    ' re-thrown by the system at the end of the Catch clause.   
Finally  
    ' Clean-up code can go here.  
End Try  
' Do not put clean-up code here, because the exception   
' is rethrown at the end of the Finally clause.  
```  
  
```csharp  
try   
{  
    // Code that is executing when the thread is aborted.  
}   
catch (ThreadAbortException ex)   
{  
    // Clean-up code can go here.  
    // If there is no Finally clause, ThreadAbortException is  
    // re-thrown by the system at the end of the Catch clause.   
}  
// Do not put clean-up code here, because the exception   
// is rethrown at the end of the Finally clause.  
```  
  
 Il codice di pulizia deve essere nel `catch` clausola o `finally` clausola, perché un <xref:System.Threading.ThreadAbortException> viene nuovamente generata dal sistema alla fine del `finally` clausola, o alla fine del `catch` clausola se è presente alcun `finally` clausola.  
  
 È possibile impedire che il sistema rigenerare l'eccezione chiamando il <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> metodo. Tuttavia, deve farlo solo se il proprio codice che ha causato il <xref:System.Threading.ThreadAbortException>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 [Utilizzo di thread e threading](../../../docs/standard/threading/using-threads-and-threading.md)
