---
title: Istruzione lock - Riferimenti per C#
ms.custom: seodec18
description: Usare l'istruzione lock C# per sincronizzare l'accesso dei thread alla risorsa condivisa
ms.date: 10/01/2018
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 7ae19e48467bf5feca115c993c2299c1ecbaadc7
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566337"
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="a61d9-103">Istruzione lock (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a61d9-103">lock statement (C# reference)</span></span>

<span data-ttu-id="a61d9-104">L'istruzione `lock` acquisisce il blocco a esclusione reciproca per un oggetto specificato, esegue un blocco di istruzioni e quindi rilascia il blocco.</span><span class="sxs-lookup"><span data-stu-id="a61d9-104">The `lock` statement acquires the mutual-exclusion lock for a given object, executes a statement block, and then releases the lock.</span></span> <span data-ttu-id="a61d9-105">Mentre è attivo un blocco, il thread che contiene il blocco può ancora acquisire e rilasciare il blocco.</span><span class="sxs-lookup"><span data-stu-id="a61d9-105">While a lock is held, the thread that holds the lock can again acquire and release the lock.</span></span> <span data-ttu-id="a61d9-106">Gli altri thread non possono acquisire il blocco e devono attendere finché il blocco non viene rilasciato.</span><span class="sxs-lookup"><span data-stu-id="a61d9-106">Any other thread is blocked from acquiring the lock and waits until the lock is released.</span></span>

<span data-ttu-id="a61d9-107">L'istruzione `lock` ha il formato</span><span class="sxs-lookup"><span data-stu-id="a61d9-107">The `lock` statement is of the form</span></span>

```csharp
lock (x)
{
    // Your code...
}
```

<span data-ttu-id="a61d9-108">in cui `x` è un'espressione di un [tipo riferimento](reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="a61d9-108">where `x` is an expression of a [reference type](reference-types.md).</span></span> <span data-ttu-id="a61d9-109">È esattamente equivalente a</span><span class="sxs-lookup"><span data-stu-id="a61d9-109">It's precisely equivalent to</span></span>

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

<span data-ttu-id="a61d9-110">Poiché il codice usa un blocco [try... finally](try-finally.md), il blocco viene rilasciato anche se viene generata un'eccezione nel corpo di un'istruzione `lock`.</span><span class="sxs-lookup"><span data-stu-id="a61d9-110">Since the code uses a [try...finally](try-finally.md) block, the lock is released even if an exception is thrown within the body of a `lock` statement.</span></span>

<span data-ttu-id="a61d9-111">Non è possibile usare la parola chiave [await](await.md) nel corpo di un'istruzione `lock`.</span><span class="sxs-lookup"><span data-stu-id="a61d9-111">You can't use the [await](await.md) keyword in the body of a `lock` statement.</span></span>

## <a name="remarks"></a><span data-ttu-id="a61d9-112">Note</span><span class="sxs-lookup"><span data-stu-id="a61d9-112">Remarks</span></span>

<span data-ttu-id="a61d9-113">Quando si sincronizza l'accesso dei thread a una risorsa condivisa, applicare il blocco a un'istanza dell'oggetto dedicata (ad esempio `private readonly object balanceLock = new object();`) o a un'altra istanza che ha poche probabilità di essere usata come oggetto di blocco da parti del codice non correlate.</span><span class="sxs-lookup"><span data-stu-id="a61d9-113">When you synchronize thread access to a shared resource, lock on a dedicated object instance (for example, `private readonly object balanceLock = new object();`) or another instance that is unlikely to be used as a lock object by unrelated parts of the code.</span></span> <span data-ttu-id="a61d9-114">Evitare di usare la stessa istanza di oggetto di blocco per diverse risorse condivise. Questo può originare problemi di deadlock o conflitti di blocco.</span><span class="sxs-lookup"><span data-stu-id="a61d9-114">Avoid using the same lock object instance for different shared resources, as it might result in deadlock or lock contention.</span></span> <span data-ttu-id="a61d9-115">In particolare, evitare di usare gli elementi seguenti come oggetti di blocco:</span><span class="sxs-lookup"><span data-stu-id="a61d9-115">In particular, avoid using the following as lock objects:</span></span>

- <span data-ttu-id="a61d9-116">`this`, perché potrebbe essere usato dai chiamanti come blocco.</span><span class="sxs-lookup"><span data-stu-id="a61d9-116">`this`, as it might be used by the callers as a lock.</span></span>
- <span data-ttu-id="a61d9-117">Istanze <xref:System.Type>, in quanto possono essere ottenute dall'operatore [typeof](../operators/type-testing-and-cast.md#typeof-operator) o dalla reflection.</span><span class="sxs-lookup"><span data-stu-id="a61d9-117"><xref:System.Type> instances, as those might be obtained by the [typeof](../operators/type-testing-and-cast.md#typeof-operator) operator or reflection.</span></span>
- <span data-ttu-id="a61d9-118">Istanze stringa, tra cui i valori letterali stringa, in quanto potrebbero essere [centralizzate](/dotnet/api/system.string.intern#remarks).</span><span class="sxs-lookup"><span data-stu-id="a61d9-118">string instances, including string literals, as those might be [interned](/dotnet/api/system.string.intern#remarks).</span></span>

## <a name="example"></a><span data-ttu-id="a61d9-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="a61d9-119">Example</span></span>

<span data-ttu-id="a61d9-120">L'esempio seguente definisce una classe `Account` che sincronizza l'accesso al proprio campo `balance` privato applicando il blocco su un'istanza `balanceLock` dedicata.</span><span class="sxs-lookup"><span data-stu-id="a61d9-120">The following example defines an `Account` class that synchronizes access to its private `balance` field by locking on a dedicated `balanceLock` instance.</span></span> <span data-ttu-id="a61d9-121">L'uso della stessa istanza per il blocco garantisce che il campo `balance` non possa essere aggiornato contemporaneamente da due thread che provano a chiamare i metodi `Debit` o `Credit` allo stesso tempo.</span><span class="sxs-lookup"><span data-stu-id="a61d9-121">Using the same instance for locking ensures that the `balance` field cannot be updated simultaneously by two threads attempting to call the `Debit` or `Credit` methods simultaneously.</span></span>

[!code-csharp[lock-statement-example](~/samples/snippets/csharp/keywords/LockStatementExample.cs)]

## <a name="c-language-specification"></a><span data-ttu-id="a61d9-122">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a61d9-122">C# language specification</span></span>

<span data-ttu-id="a61d9-123">Per altre informazioni, vedere la sezione [Istruzione lock](~/_csharplang/spec/statements.md#the-lock-statement) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="a61d9-123">For more information, see [The lock statement](~/_csharplang/spec/statements.md#the-lock-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a61d9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a61d9-124">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="a61d9-125">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a61d9-125">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a61d9-126">Parole chiave C#</span><span class="sxs-lookup"><span data-stu-id="a61d9-126">C# keywords</span></span>](index.md)
- [<span data-ttu-id="a61d9-127">Cenni preliminari sulle primitive di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="a61d9-127">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)
