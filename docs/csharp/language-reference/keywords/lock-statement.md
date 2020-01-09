---
title: Istruzione lock - Riferimenti per C#
description: Usare l'istruzione lock C# per sincronizzare l'accesso dei thread alla risorsa condivisa
ms.date: 10/01/2018
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 467881dd36c97b6b18b7f31d4e4af25152b0d012
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713394"
---
# <a name="lock-statement-c-reference"></a>Istruzione lock (Riferimenti per C#)

L'istruzione `lock` acquisisce il blocco a esclusione reciproca per un oggetto specificato, esegue un blocco di istruzioni e quindi rilascia il blocco. Mentre è attivo un blocco, il thread che contiene il blocco può ancora acquisire e rilasciare il blocco. Gli altri thread non possono acquisire il blocco e devono attendere finché il blocco non viene rilasciato.

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

Non è possibile usare l'[operatore await](../operators/await.md) nel corpo di un'istruzione `lock`.

## <a name="remarks"></a>Note

Quando si sincronizza l'accesso dei thread a una risorsa condivisa, applicare il blocco a un'istanza dell'oggetto dedicata (ad esempio `private readonly object balanceLock = new object();`) o a un'altra istanza che ha poche probabilità di essere usata come oggetto di blocco da parti del codice non correlate. Evitare di usare la stessa istanza di oggetto di blocco per diverse risorse condivise. Questo può originare problemi di deadlock o conflitti di blocco. In particolare, evitare di usare gli elementi seguenti come oggetti di blocco:

- `this`, perché potrebbe essere usato dai chiamanti come blocco.
- Istanze <xref:System.Type>, in quanto possono essere ottenute dall'operatore [typeof](../operators/type-testing-and-cast.md#typeof-operator) o dalla reflection.
- Istanze stringa, tra cui i valori letterali stringa, in quanto potrebbero essere [centralizzate](/dotnet/api/system.string.intern#remarks).

## <a name="example"></a>Esempio

L'esempio seguente definisce una classe `Account` che sincronizza l'accesso al proprio campo `balance` privato applicando il blocco su un'istanza `balanceLock` dedicata. L'uso della stessa istanza per il blocco garantisce che il campo `balance` non possa essere aggiornato contemporaneamente da due thread che provano a chiamare i metodi `Debit` o `Credit` allo stesso tempo.

[!code-csharp[lock-statement-example](~/samples/snippets/csharp/keywords/LockStatementExample.cs)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Istruzione lock](~/_csharplang/spec/statements.md#the-lock-statement) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [Riferimenti per C#](../index.md)
- [Parole chiave C#](index.md)
- [Cenni preliminari sulle primitive di sincronizzazione](../../../standard/threading/overview-of-synchronization-primitives.md)
