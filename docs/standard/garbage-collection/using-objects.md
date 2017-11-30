---
title: Uso di oggetti che implementano IDisposable
ms.custom: 
ms.date: 04/07/2017
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
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fd78c2f99ca5c8ffe3c753e158ceba3e0c458c5b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="using-objects-that-implement-idisposable"></a>Uso di oggetti che implementano IDisposable

Garbage collector di common language runtime recupera la memoria utilizzata dagli oggetti gestiti, ma i tipi che utilizzano risorse non gestite implementano la <xref:System.IDisposable> interfaccia per consentire la memoria allocata a queste risorse non gestite essere recuperato. Dopo avere utilizzato un oggetto che implementa <xref:System.IDisposable>, è necessario chiamare l'implementazione <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> dell'oggetto. Questa operazione può essere eseguita in due modi:  
  
* Con l'istruzione `using` in C# o l'istruzione `Using` in Visual Basic.  
  
* Implementando un blocco `try/finally`.  

## <a name="the-using-statement"></a>Istruzione using

L'istruzione `using` in C# e l'istruzione `Using` in Visual Basic semplificano il codice da scrivere per creare e pulire un oggetto. L'istruzione `using` ottiene una o più risorse, esegue le istruzioni specificate ed elimina l'oggetto in modo automatico. L'istruzione `using` è comunque utile solo per gli oggetti usati nell'ambito del metodo in cui vengono costruiti.  
  
Nell'esempio seguente viene utilizzata l'istruzione `using` per creare e rilasciare un oggetto <xref:System.IO.StreamReader?displayProperty=nameWithType>.  
  
[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]  
  
Si noti che, anche se la classe <xref:System.IO.StreamReader> implementa l'interfaccia <xref:System.IDisposable>, a indicare che utilizza una risorsa non gestita, nell'esempio non viene chiamato il metodo <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> in modo esplicito. Quando nel compilatore C# o Visual Basic viene rilevata l'istruzione `using`, viene generato il linguaggio intermedio (IL) equivalente al codice seguente, che contiene un blocco `try/finally` in modo esplicito.  
  
[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]  
  
C# `using` istruzione consente inoltre di ottenere più risorse in un'unica istruzione, che equivale internamente nidificati `using` istruzioni. Nell'esempio seguente viene creata l'istanza di due oggetti <xref:System.IO.StreamReader> per leggere il contenuto di due diversi file.  
  
[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a>Blocco try/finally

Anziché eseguire il wrapping di un blocco `try/finally` in un'istruzione `using`, è possibile implementare direttamente il blocco `try/finally`. La scelta può essere espressione dello stile di codifica personale oppure essere dovuta a uno dei seguenti motivi:  
  
* Includere un blocco `catch` per gestire eventuali eccezioni generate nel blocco `try`. In caso contrario, tutte le eccezioni generate dall'istruzione `using` non vengono gestite, analogamente alle eccezioni generate all'interno del blocco `using` se un blocco `try/catch` non è presente.  
  
* Creare un'istanza di un oggetto che implementa <xref:System.IDisposable> il cui ambito non è locale rispetto al blocco in cui viene dichiarato.  
  
Nell'esempio seguente è simile all'esempio precedente, ad eccezione del fatto che usa un `try/catch/finally` blocco per creare un'istanza, utilizzare ed eliminare risorse una <xref:System.IO.StreamReader> oggetto e per gestire le eccezioni generate dal <xref:System.IO.StreamReader> costruttore e il relativo <xref:System.IO.StreamReader.ReadToEnd%2A> metodo. Si noti che il codice nel blocco `finally` controlla che l'oggetto che implementa <xref:System.IDisposable> non sia `null` prima di chiamare il metodo <xref:System.IDisposable.Dispose%2A>. L'omissione di tale controllo può provocare un'eccezione <xref:System.NullReferenceException> in fase di esecuzione.  
  
[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]  
  
È possibile seguire questo modello di base se sceglie di implementare o è necessario implementare un `try/finally` blocco, perché non supporta il linguaggio di programmazione un `using` istruzione ma consente chiamate dirette al <xref:System.IDisposable.Dispose%2A> metodo. 
  
## <a name="see-also"></a>Vedere anche

[Pulizia delle risorse non gestite](../../../docs/standard/garbage-collection/unmanaged.md)   
[Istruzione using (riferimenti per c#)](~/docs/csharp/language-reference/keywords/using-statement.md)   
[Utilizzando l'istruzione (Visual Basic)](~/docs/visual-basic/language-reference/statements/using-statement.md)
