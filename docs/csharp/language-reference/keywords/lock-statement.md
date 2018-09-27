---
title: Istruzione lock (Riferimenti per C#)
description: Usare l'istruzione lock di C# per sincronizzare l'accesso dei thread alla risorsa condivisa
ms.date: 08/28/2018
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 2b6fbfb2f81d7745c4effb9ea0087f34cc872a6c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858356"
---
# <a name="lock-statement-c-reference"></a>Istruzione lock (Riferimenti per C#)

L'istruzione `lock` ottiene il blocco a esclusione reciproca per un oggetto specificato, esegue il blocco di un'istruzione e quindi rilascia il blocco. Mentre è attivo un blocco, il thread che contiene il blocco può ancora ottenere e rilasciare il blocco. Gli altri thread non possono ottenere il blocco e devono attendere finché il blocco non viene rilasciato.

L'istruzione `lock` ha il formato

```csharp
lock (x)
{
    // Your code...
}
```

in cui `x` è un'espressione di un [tipo riferimento](reference-types.md). È esattamente equivalente a

```csharp
object __lockObj = x;
bool __lockWasTaken = false;
try
{
    System.Threading.Monitor.Enter(__lockObj, ref __lockWasTaken);
    // Your code...
}
finally
{
    if (__lockWasTaken) System.Threading.Monitor.Exit(__lockObj);
}
```

Poiché il codice usa un blocco [try... finally](try-finally.md), il blocco viene rilasciato anche se viene generata un'eccezione nel corpo di un'istruzione `lock`.

Non è possibile usare la parola chiave [await](await.md) nel corpo di un'istruzione `lock`.

## <a name="remarks"></a>Note

Quando si sincronizza l'accesso thread a una risorsa condivisa, applicare il blocco a un'istanza dell'oggetto dedicata (ad esempio `private readonly object balanceLock = new object();`) o a un'altra istanza che ha poche probabilità di essere usata come oggetto di blocco da parti del codice non correlate. Evitare di usare la stessa istanza di oggetto di blocco per diverse risorse condivise. Questo può originare problemi di deadlock o conflitti di blocco. In particolare evitare di usare

- `this` (usabile dai chiamati come blocco),
- istanze <xref:System.Type> (possono essere ottenute dall'operatore [typeof](typeof.md) o dalla reflection),
- e infine istanze stringa, tra cui i valori letterali stringa,

come oggetti di blocco.

## <a name="example"></a>Esempio

L'esempio seguente definisce una classe `Account` che sincronizza l'accesso al proprio campo `balance` privato applicando il blocco su un'istanza `balanceLock` dedicata. L'uso della stessa istanza per il blocco garantisce che il campo `balance` non possa essere aggiornato contemporaneamente da due thread che provano a chiamare i metodi `Debit` o `Credit` allo stesso tempo.

[!code-csharp[lock-statement-example](~/samples/snippets/csharp/keywords/LockStatementExample.cs)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [Riferimenti per C#](../index.md)
- [Parole chiave di C#](index.md)
- [Parole chiave per le istruzioni](statement-keywords.md)
- [Operazioni interlocked](../../../standard/threading/interlocked-operations.md)
- [Cenni preliminari sulle primitive di sincronizzazione](../../../standard/threading/overview-of-synchronization-primitives.md)