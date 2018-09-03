---
title: Istruzione lock (Riferimenti per C#)
description: 'La parola chiave lock viene usata nel threading '
ms.date: 07/20/2015
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 6ed46837482642dfd7e1a96cd120fc18023c5e9f
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931193"
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="e00cf-103">Istruzione lock (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e00cf-103">lock statement (C# Reference)</span></span>

<span data-ttu-id="e00cf-104">La parola chiave `lock` contrassegna un blocco di istruzioni come sezione critica ottenendo il blocco a esclusione reciproca per un determinato oggetto, eseguendo un'istruzione e rilasciando in seguito il blocco.</span><span class="sxs-lookup"><span data-stu-id="e00cf-104">The `lock` keyword marks a statement block as a critical section by obtaining the mutual-exclusion lock for a given object, executing a statement, and then releasing the lock.</span></span> <span data-ttu-id="e00cf-105">L'esempio seguente illustra un'istruzione `lock`.</span><span class="sxs-lookup"><span data-stu-id="e00cf-105">The following example includes a `lock` statement.</span></span>

```csharp
class Account
{
    decimal balance;
    private Object thisLock = new Object();

    public void Withdraw(decimal amount)
    {
        lock (thisLock)
        {
            if (amount > balance)
            {
                throw new Exception("Insufficient funds");
            }
            balance -= amount;
        }
    }
}
```

<span data-ttu-id="e00cf-106">Per altre informazioni, vedere [Sincronizzazione di thread](../../programming-guide/concepts/threading/thread-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="e00cf-106">For more information, see [Thread Synchronization](../../programming-guide/concepts/threading/thread-synchronization.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="e00cf-107">Note</span><span class="sxs-lookup"><span data-stu-id="e00cf-107">Remarks</span></span>

<span data-ttu-id="e00cf-108">La parola chiave `lock` impedisce a un thread di entrare in una sezione critica del codice se è già presente un altro thread.</span><span class="sxs-lookup"><span data-stu-id="e00cf-108">The `lock` keyword ensures that one thread does not enter a critical section of code while another thread is in the critical section.</span></span> <span data-ttu-id="e00cf-109">Se un altro thread tenta di accedere a un codice bloccato, attenderà (in stato di blocco) finché l'oggetto non verrà rilasciato.</span><span class="sxs-lookup"><span data-stu-id="e00cf-109">If another thread tries to enter a locked code, it will wait, block, until the object is released.</span></span>

<span data-ttu-id="e00cf-110">Nella sezione [Threading](../../programming-guide/concepts/threading/index.md) vengono specificate informazioni sul threading.</span><span class="sxs-lookup"><span data-stu-id="e00cf-110">The section [Threading](../../programming-guide/concepts/threading/index.md) discusses threading.</span></span>

<span data-ttu-id="e00cf-111">La parola chiave `lock` chiama <xref:System.Threading.Monitor.Enter%2A> all'inizio del blocco e <xref:System.Threading.Monitor.Exit%2A> alla fine del blocco.</span><span class="sxs-lookup"><span data-stu-id="e00cf-111">The `lock` keyword calls <xref:System.Threading.Monitor.Enter%2A> at the start of the block and <xref:System.Threading.Monitor.Exit%2A> at the end of the block.</span></span> <span data-ttu-id="e00cf-112">Viene generata un'eccezione <xref:System.Threading.ThreadInterruptedException> se <xref:System.Threading.Thread.Interrupt%2A> interrompe un thread in attesa di immettere un'istruzione `lock`.</span><span class="sxs-lookup"><span data-stu-id="e00cf-112">A <xref:System.Threading.ThreadInterruptedException> is thrown if <xref:System.Threading.Thread.Interrupt%2A> interrupts a thread that is waiting to enter a `lock` statement.</span></span>

<span data-ttu-id="e00cf-113">In generale è opportuno evitare il blocco su un tipo `public` o su istanze oltre il controllo del codice.</span><span class="sxs-lookup"><span data-stu-id="e00cf-113">In general, avoid locking on a `public` type, or instances beyond your code's control.</span></span> <span data-ttu-id="e00cf-114">I costrutti comuni `lock (this)`, `lock (typeof (MyType))` e `lock ("myLock")` non rispettano questa regola:</span><span class="sxs-lookup"><span data-stu-id="e00cf-114">The common constructs `lock (this)`, `lock (typeof (MyType))`, and `lock ("myLock")` violate this guideline:</span></span>

- <span data-ttu-id="e00cf-115">`lock (this)` costituisce un problema se l'accesso all'istanza può avvenire pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="e00cf-115">`lock (this)` is a problem if the instance can be accessed publicly.</span></span>

- <span data-ttu-id="e00cf-116">`lock (typeof (MyType))` costituisce un problema se l'accesso a `MyType` può avvenire pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="e00cf-116">`lock (typeof (MyType))` is a problem if `MyType` is publicly accessible.</span></span>

- <span data-ttu-id="e00cf-117">`lock("myLock")` costituisce un problema poiché qualsiasi altro codice nel processo che usa la stessa stringa condividerà lo stesso blocco.</span><span class="sxs-lookup"><span data-stu-id="e00cf-117">`lock("myLock")` is a problem because any other code in the process using the same string, will share the same lock.</span></span>

<span data-ttu-id="e00cf-118">La procedura consigliata consiste nel definire un oggetto `private` da bloccare o una variabile oggetto `private static` per proteggere i dati comuni a tutte le istanze.</span><span class="sxs-lookup"><span data-stu-id="e00cf-118">Best practice is to define a `private` object to lock on, or a `private static` object variable to protect data common to all instances.</span></span>

<span data-ttu-id="e00cf-119">Non è possibile usare la parola chiave [await](await.md) nel corpo di un'istruzione `lock`.</span><span class="sxs-lookup"><span data-stu-id="e00cf-119">You can't use the [await](await.md) keyword in the body of a `lock` statement.</span></span>

## <a name="example---threads-without-locking"></a><span data-ttu-id="e00cf-120">Esempio - Thread senza blocco</span><span class="sxs-lookup"><span data-stu-id="e00cf-120">Example - Threads without locking</span></span>

<span data-ttu-id="e00cf-121">L'esempio seguente illustra un uso semplificato dei thread senza blocco in C#:</span><span class="sxs-lookup"><span data-stu-id="e00cf-121">The following sample shows a simple use of threads without locking in C#:</span></span>

[!code-csharp[csrefKeywordsFixedLock#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsFixedLock/CS/csrefKeywordsFixedLock.cs#5)]

## <a name="example---threads-using-locking"></a><span data-ttu-id="e00cf-122">Esempio - Thread con blocco</span><span class="sxs-lookup"><span data-stu-id="e00cf-122">Example - Threads using locking</span></span>

<span data-ttu-id="e00cf-123">Nell'esempio riportato di seguito vengono usati thread e `lock`.</span><span class="sxs-lookup"><span data-stu-id="e00cf-123">The following sample uses threads and `lock`.</span></span> <span data-ttu-id="e00cf-124">Finché è presente l'istruzione `lock`, il blocco di istruzioni rimarrà una sezione critica e `balance` non diventerà mai un numero negativo:</span><span class="sxs-lookup"><span data-stu-id="e00cf-124">As long as the `lock` statement is present, the statement block is a critical section and `balance` will never become a negative number:</span></span>

[!code-csharp[csrefKeywordsFixedLock#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsFixedLock/CS/csrefKeywordsFixedLock.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="e00cf-125">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e00cf-125">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e00cf-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e00cf-126">See also</span></span>

- <xref:System.Reflection.MethodImplAttributes>
- <xref:System.Threading.Mutex>
- <xref:System.Threading.Monitor>
- [<span data-ttu-id="e00cf-127">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e00cf-127">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="e00cf-128">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e00cf-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e00cf-129">Threading</span><span class="sxs-lookup"><span data-stu-id="e00cf-129">Threading</span></span>](../../programming-guide/concepts/threading/index.md)
- [<span data-ttu-id="e00cf-130">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="e00cf-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e00cf-131">Parole chiave per le istruzioni</span><span class="sxs-lookup"><span data-stu-id="e00cf-131">Statement Keywords</span></span>](statement-keywords.md)
- [<span data-ttu-id="e00cf-132">Operazioni interlocked</span><span class="sxs-lookup"><span data-stu-id="e00cf-132">Interlocked Operations</span></span>](../../../standard/threading/interlocked-operations.md)
- [<span data-ttu-id="e00cf-133">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="e00cf-133">AutoResetEvent</span></span>](../../../standard/threading/autoresetevent.md)
- [<span data-ttu-id="e00cf-134">Sincronizzazione di thread</span><span class="sxs-lookup"><span data-stu-id="e00cf-134">Thread Synchronization</span></span>](../../programming-guide/concepts/threading/thread-synchronization.md)