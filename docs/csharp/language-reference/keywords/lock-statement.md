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
# <a name="lock-statement-c-reference"></a><span data-ttu-id="d62cf-103">Istruzione lock (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="d62cf-103">lock statement (C# Reference)</span></span>

<span data-ttu-id="d62cf-104">L'istruzione `lock` ottiene il blocco a esclusione reciproca per un oggetto specificato, esegue il blocco di un'istruzione e quindi rilascia il blocco.</span><span class="sxs-lookup"><span data-stu-id="d62cf-104">The `lock` statement obtains the mutual-exclusion lock for a given object, executes a statement block, and then releases the lock.</span></span> <span data-ttu-id="d62cf-105">Mentre è attivo un blocco, il thread che contiene il blocco può ancora ottenere e rilasciare il blocco.</span><span class="sxs-lookup"><span data-stu-id="d62cf-105">While a lock is held, the thread that holds the lock can again obtain and release the lock.</span></span> <span data-ttu-id="d62cf-106">Gli altri thread non possono ottenere il blocco e devono attendere finché il blocco non viene rilasciato.</span><span class="sxs-lookup"><span data-stu-id="d62cf-106">Any other thread is blocked from obtaining the lock and waits until the lock is released.</span></span>

<span data-ttu-id="d62cf-107">L'istruzione `lock` ha il formato</span><span class="sxs-lookup"><span data-stu-id="d62cf-107">The `lock` statement is of the form</span></span>

```csharp
lock (x)
{
    // Your code...
}
```

<span data-ttu-id="d62cf-108">in cui `x` è un'espressione di un [tipo riferimento](reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="d62cf-108">where `x` is an expression of a [reference type](reference-types.md).</span></span> <span data-ttu-id="d62cf-109">È esattamente equivalente a</span><span class="sxs-lookup"><span data-stu-id="d62cf-109">It's precisely equivalent to</span></span>

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

<span data-ttu-id="d62cf-110">Poiché il codice usa un blocco [try... finally](try-finally.md), il blocco viene rilasciato anche se viene generata un'eccezione nel corpo di un'istruzione `lock`.</span><span class="sxs-lookup"><span data-stu-id="d62cf-110">Since the code uses a [try...finally](try-finally.md) block, the lock is released even if an exception is thrown within the body of a `lock` statement.</span></span>

<span data-ttu-id="d62cf-111">Non è possibile usare la parola chiave [await](await.md) nel corpo di un'istruzione `lock`.</span><span class="sxs-lookup"><span data-stu-id="d62cf-111">You can't use the [await](await.md) keyword in the body of a `lock` statement.</span></span>

## <a name="remarks"></a><span data-ttu-id="d62cf-112">Note</span><span class="sxs-lookup"><span data-stu-id="d62cf-112">Remarks</span></span>

<span data-ttu-id="d62cf-113">Quando si sincronizza l'accesso thread a una risorsa condivisa, applicare il blocco a un'istanza dell'oggetto dedicata (ad esempio `private readonly object balanceLock = new object();`) o a un'altra istanza che ha poche probabilità di essere usata come oggetto di blocco da parti del codice non correlate.</span><span class="sxs-lookup"><span data-stu-id="d62cf-113">When you synchronize thread access to shared resource, lock on a dedicated object instance (for example, `private readonly object balanceLock = new object();`) or another instance that is unlikely to be used as a lock object by unrelated parts of the code.</span></span> <span data-ttu-id="d62cf-114">Evitare di usare la stessa istanza di oggetto di blocco per diverse risorse condivise. Questo può originare problemi di deadlock o conflitti di blocco.</span><span class="sxs-lookup"><span data-stu-id="d62cf-114">Avoid using the same lock object instance for different shared resources, as it might result in deadlock or lock contention.</span></span> <span data-ttu-id="d62cf-115">In particolare evitare di usare</span><span class="sxs-lookup"><span data-stu-id="d62cf-115">In particular, avoid using</span></span>

- <span data-ttu-id="d62cf-116">`this` (usabile dai chiamati come blocco),</span><span class="sxs-lookup"><span data-stu-id="d62cf-116">`this` (might be used by the callers as a lock),</span></span>
- <span data-ttu-id="d62cf-117">istanze <xref:System.Type> (possono essere ottenute dall'operatore [typeof](typeof.md) o dalla reflection),</span><span class="sxs-lookup"><span data-stu-id="d62cf-117"><xref:System.Type> instances (might be obtained by the [typeof](typeof.md) operator or reflection),</span></span>
- <span data-ttu-id="d62cf-118">e infine istanze stringa, tra cui i valori letterali stringa,</span><span class="sxs-lookup"><span data-stu-id="d62cf-118">string instances, including string literals,</span></span>

<span data-ttu-id="d62cf-119">come oggetti di blocco.</span><span class="sxs-lookup"><span data-stu-id="d62cf-119">as lock objects.</span></span>

## <a name="example"></a><span data-ttu-id="d62cf-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="d62cf-120">Example</span></span>

<span data-ttu-id="d62cf-121">L'esempio seguente definisce una classe `Account` che sincronizza l'accesso al proprio campo `balance` privato applicando il blocco su un'istanza `balanceLock` dedicata.</span><span class="sxs-lookup"><span data-stu-id="d62cf-121">The following example defines an `Account` class that synchronizes access to its private `balance` field by locking on a dedicated `balanceLock` instance.</span></span> <span data-ttu-id="d62cf-122">L'uso della stessa istanza per il blocco garantisce che il campo `balance` non possa essere aggiornato contemporaneamente da due thread che provano a chiamare i metodi `Debit` o `Credit` allo stesso tempo.</span><span class="sxs-lookup"><span data-stu-id="d62cf-122">Using the same instance for locking ensures that the `balance` field cannot be updated simultaneously by two threads attempting to call the `Debit` or `Credit` methods simultaneously.</span></span>

[!code-csharp[lock-statement-example](~/samples/snippets/csharp/keywords/LockStatementExample.cs)]

## <a name="c-language-specification"></a><span data-ttu-id="d62cf-123">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d62cf-123">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d62cf-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d62cf-124">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="d62cf-125">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="d62cf-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d62cf-126">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="d62cf-126">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d62cf-127">Parole chiave per le istruzioni</span><span class="sxs-lookup"><span data-stu-id="d62cf-127">Statement Keywords</span></span>](statement-keywords.md)
- [<span data-ttu-id="d62cf-128">Operazioni interlocked</span><span class="sxs-lookup"><span data-stu-id="d62cf-128">Interlocked operations</span></span>](../../../standard/threading/interlocked-operations.md)
- [<span data-ttu-id="d62cf-129">Cenni preliminari sulle primitive di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="d62cf-129">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)