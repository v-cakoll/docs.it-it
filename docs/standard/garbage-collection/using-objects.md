---
title: Uso di oggetti che implementano IDisposable
ms.date: 05/13/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
ms.openlocfilehash: 87eefe2bd347ba1564b2f06d49bbee3b85efdb97
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287597"
---
# <a name="using-objects-that-implement-idisposable"></a>Uso di oggetti che implementano IDisposable

Il Garbage Collector di Common Language Runtime recupera la memoria usata dagli oggetti gestiti, ma i tipi che usano risorse non gestite implementano l' <xref:System.IDisposable> interfaccia per consentire il rimborso delle risorse necessarie per queste risorse non gestite. Dopo avere utilizzato un oggetto che implementa <xref:System.IDisposable>, è necessario chiamare l'implementazione <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> dell'oggetto. Questa operazione può essere eseguita in due modi:

- Con l' `using` istruzione C# ( `Using` in Visual Basic).
- Implementando un `try/finally` blocco e chiamando l'oggetto <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> in `finally` .

## <a name="the-using-statement"></a>Istruzione using

L' [ `using` istruzione](../../csharp/language-reference/keywords/using-statement.md) in C# e l' [ `Using` istruzione](../../visual-basic/language-reference/statements/using-statement.md) in Visual Basic semplificano il codice che è necessario scrivere per pulire un oggetto. L'istruzione `using` ottiene una o più risorse, esegue le istruzioni specificate ed elimina l'oggetto in modo automatico. L'istruzione `using` è comunque utile solo per gli oggetti usati nell'ambito del metodo in cui vengono costruiti.

Nell'esempio seguente viene utilizzata l'istruzione `using` per creare e rilasciare un oggetto <xref:System.IO.StreamReader?displayProperty=nameWithType>.

[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]

Sebbene la <xref:System.IO.StreamReader> classe implementi l' <xref:System.IDisposable> interfaccia, che indica che usa una risorsa non gestita, nell'esempio non viene chiamato in modo esplicito il <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> metodo. Quando nel compilatore C# o Visual Basic viene rilevata l'istruzione `using`, viene generato il linguaggio intermedio (IL) equivalente al codice seguente, che contiene un blocco `try/finally` in modo esplicito.

[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]

L'istruzione `using` C# è consente anche di acquisire più risorse in un'unica istruzione, che equivale internamente all'uso di più istruzioni `using` annidate. Nell'esempio seguente viene creata l'istanza di due oggetti <xref:System.IO.StreamReader> per leggere il contenuto di due diversi file.

[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a>Blocco try/finally

Anziché eseguire il wrapping di un blocco `try/finally` in un'istruzione `using`, è possibile implementare direttamente il blocco `try/finally`. Potrebbe trattarsi dello stile di codifica personale oppure è possibile eseguire questa operazione per uno dei motivi seguenti:

- Per includere un `catch` blocco per gestire le eccezioni generate nel `try` blocco. In caso contrario, tutte le eccezioni generate all'interno dell' `using` istruzione non vengono gestite.

- Creare un'istanza di un oggetto che implementa <xref:System.IDisposable> il cui ambito non è locale rispetto al blocco in cui viene dichiarato.

L'esempio seguente è simile a quello precedente, con la differenza che in questo viene usato un blocco `try/catch/finally` per creare un'istanza di un oggetto <xref:System.IO.StreamReader>, utilizzarla ed eliminarla e per gestire le eccezioni generate dal costruttore <xref:System.IO.StreamReader> e dal relativo metodo <xref:System.IO.StreamReader.ReadToEnd%2A>. Il codice nel `finally` blocco controlla che l'oggetto che implementa <xref:System.IDisposable> non sia `null` prima di chiamare il <xref:System.IDisposable.Dispose%2A> metodo. L'omissione di tale controllo può provocare un'eccezione <xref:System.NullReferenceException> in fase di esecuzione.

[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]

È possibile usare questo modello di base se si decide di implementare o è necessario implementare un blocco `try/finally`, poiché il linguaggio di programmazione non supporta un'istruzione `using` ma consente chiamate dirette al metodo <xref:System.IDisposable.Dispose%2A>.

## <a name="idisposable-instance-members"></a>Membri di istanza IDisposable

Se una classe include un' <xref:System.IDisposable> implementazione come membro di istanza, ovvero un campo o una proprietà, la classe deve implementare anche <xref:System.IDisposable> . Per altre informazioni, vedere [implementare un'eliminazione a catena](implementing-dispose.md#cascade-dispose-calls).

## <a name="see-also"></a>Vedere anche

- [Pulizia delle risorse non gestite](unmanaged.md)
- [Istruzione using (riferimenti per C#)](../../csharp/language-reference/keywords/using-statement.md)
- [Istruzione using (Visual Basic)](../../visual-basic/language-reference/statements/using-statement.md)
