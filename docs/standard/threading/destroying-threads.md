---
title: Eliminazione definitiva di thread
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
ms.openlocfilehash: 842ca4ff17f9cbab3a1518d2dea37436c9b23f9d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78155932"
---
# <a name="destroying-threads"></a>Eliminazione definitiva di thread

Per terminare l'esecuzione del thread, in genere si utilizza il modello di [annullamento cooperativo.](cancellation-in-managed-threads.md) A volte non è possibile arrestare un thread in modo cooperativo, perché esegue codice di terze parti non progettato per l'annullamento cooperativo. Il <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> metodo in .NET Framework può essere utilizzato per terminare un thread gestito con la coattività. Quando si <xref:System.Threading.Thread.Abort%2A>chiama , Common Language <xref:System.Threading.ThreadAbortException> Runtime genera un nel thread di destinazione, che il thread di destinazione può intercettare. Per altre informazioni, vedere <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>. Il <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> metodo non è supportato in .NET Core.The method is not supported in .NET Core. Se è necessario terminare l'esecuzione di codice di terze parti con la coattività <xref:System.Diagnostics.Process.Kill%2A?displayProperty=nameWithType>in .NET Core, eseguirlo nel processo separato e utilizzare .

> [!NOTE]
> Se un thread esegue codice non gestito quando viene chiamato il metodo <xref:System.Threading.Thread.Abort%2A>, il runtime lo contrassegna come <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>. L'eccezione viene generata quando il thread torna al codice gestito.  
  
 Quando un thread viene interrotto, non può essere riavviato.  
  
 Il metodo <xref:System.Threading.Thread.Abort%2A> non determina l'interruzione immediata del thread perché il thread di destinazione può rilevare <xref:System.Threading.ThreadAbortException> ed eseguire quantità arbitrarie di codice in un blocco `finally`. È possibile chiamare <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> se è necessario attendere il completamento del thread. <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> è una chiamata di blocco che non termina finché il thread non ha effettivamente arrestato l'esecuzione o è trascorso un intervallo di timeout facoltativo. Il thread interrotto può chiamare il metodo <xref:System.Threading.Thread.ResetAbort%2A> o eseguire un'elaborazione senza vincoli in un blocco `finally`, quindi, se non si specifica un timeout, non è sicuro che l'attesa termini.  
  
 I thread in attesa di una chiamata al metodo <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> possono essere interrotti da altri thread che chiamano <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.  
  
## <a name="handling-threadabortexception"></a>Gestione di ThreadAbortException  
 Se si prevede che il thread venga interrotto, in seguito alla chiamata ad <xref:System.Threading.Thread.Abort%2A> dal codice o in seguito allo scaricamento di un dominio applicazione in cui il thread è in esecuzione (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> usa <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> per terminare i thread), il thread deve gestire <xref:System.Threading.ThreadAbortException> ed eseguire un'eventuale elaborazione finale in una clausola `finally`, come illustrato nel codice seguente.  
  
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
  
 Il codice di pulizia deve essere nella clausola `catch` o nella clausola `finally`, perché un'eccezione <xref:System.Threading.ThreadAbortException> viene nuovamente generata dal sistema alla fine della clausola `finally` o alla fine della clausola `catch` se non sono presenti clausole `finally`.  
  
 È possibile impedire che il sistema generi nuovamente l'eccezione chiamando il metodo <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType>. È tuttavia consigliabile farlo solo se il codice ha generato <xref:System.Threading.ThreadAbortException>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.ThreadAbortException>
- <xref:System.Threading.Thread>
- [Utilizzo di thread e threading](../../../docs/standard/threading/using-threads-and-threading.md)
