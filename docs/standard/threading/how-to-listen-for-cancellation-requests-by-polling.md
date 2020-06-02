---
title: 'Procedura: mettersi in ascolto di richieste di annullamento tramite polling'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
ms.openlocfilehash: 6f70ce75b1d6a3d4d7e8a38d739005a261b07241
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279556"
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a>Procedura: mettersi in ascolto di richieste di annullamento tramite polling
L'esempio seguente illustra un modo in cui il codice utente può eseguire il polling di un token di annullamento a intervalli regolari per verificare se è stato richiesto l'annullamento dal thread chiamante. Questo esempio usa il tipo <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, ma lo stesso modello si applica alle operazioni asincrone create direttamente dal tipo <xref:System.Threading.ThreadPool?displayProperty=nameWithType> o <xref:System.Threading.Thread?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  
 Il polling richiede un tipo di codice di ciclo o ricorsivo in grado di leggere periodicamente il valore della proprietà booleana <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>. Se si usa il tipo <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> e si è in attesa del completamento dell'attività nel thread chiamante, è possibile usare il metodo <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> per controllare la proprietà e generare l'eccezione. Usando questo metodo, si garantisce che venga generata l'eccezione corretta in risposta a una richiesta. Se si usa <xref:System.Threading.Tasks.Task>, chiamare questo metodo è preferibile rispetto a generare manualmente un'eccezione <xref:System.OperationCanceledException>. Se non è necessario generare l'eccezione, è sufficiente controllare la proprietà e restituire un risultato dal metodo se la proprietà è `true`.  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 La chiamata di <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> è estremamente veloce e non comporta un sovraccarico significativo nei cicli.  
  
 Se si chiama <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, è necessario controllare in modo esplicito la proprietà <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> solo se ci sono altre attività da eseguire in risposta all'annullamento oltre alla generazione dell'eccezione. In questo esempio è possibile vedere che il codice accede effettivamente alla proprietà due volte: una volta tramite accesso esplicito e di nuovo nel metodo <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>. Poiché tuttavia l'operazione di lettura della proprietà <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> comporta solo un'istruzione di lettura volatile per accesso, il doppio accesso non è significativo dal punto di vista delle prestazioni. È preferibile chiamare il metodo invece che generare manualmente l'eccezione <xref:System.OperationCanceledException>.  
  
## <a name="see-also"></a>Vedere anche

- [Annullamento in thread gestiti](cancellation-in-managed-threads.md)
