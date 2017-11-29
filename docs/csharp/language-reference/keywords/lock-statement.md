---
title: Istruzione lock (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords: lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: "43"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eb48c2b1554ad2817406eaef42b4cb336ea46862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="8f306-102">Istruzione lock (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="8f306-102">lock Statement (C# Reference)</span></span>
<span data-ttu-id="8f306-103">La parola chiave `lock` contrassegna un blocco di istruzioni come sezione critica ottenendo il blocco a esclusione reciproca per un determinato oggetto, eseguendo un'istruzione e rilasciando in seguito il blocco.</span><span class="sxs-lookup"><span data-stu-id="8f306-103">The `lock` keyword marks a statement block as a critical section by obtaining the mutual-exclusion lock for a given object, executing a statement, and then releasing the lock.</span></span> <span data-ttu-id="8f306-104">L'esempio seguente illustra un'istruzione `lock`.</span><span class="sxs-lookup"><span data-stu-id="8f306-104">The following example includes a `lock` statement.</span></span>  
  
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
  
 <span data-ttu-id="8f306-105">Per altre informazioni, vedere [Sincronizzazione di thread](../../programming-guide/concepts/threading/thread-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="8f306-105">For more information, see [Thread Synchronization](../../programming-guide/concepts/threading/thread-synchronization.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f306-106">Note</span><span class="sxs-lookup"><span data-stu-id="8f306-106">Remarks</span></span>  
 <span data-ttu-id="8f306-107">La parola chiave `lock` impedisce a un thread di entrare in una sezione critica del codice se è già presente un altro thread.</span><span class="sxs-lookup"><span data-stu-id="8f306-107">The `lock` keyword ensures that one thread does not enter a critical section of code while another thread is in the critical section.</span></span> <span data-ttu-id="8f306-108">Se un altro thread tenta di accedere a un codice bloccato, attenderà (in stato di blocco) finché l'oggetto non verrà rilasciato.</span><span class="sxs-lookup"><span data-stu-id="8f306-108">If another thread tries to enter a locked code, it will wait, block, until the object is released.</span></span>  
  
 <span data-ttu-id="8f306-109">Nella sezione [Threading](../../programming-guide/concepts/threading/index.md) vengono specificate informazioni sul threading.</span><span class="sxs-lookup"><span data-stu-id="8f306-109">The section [Threading](../../programming-guide/concepts/threading/index.md) discusses threading.</span></span>  
  
 <span data-ttu-id="8f306-110">La parola chiave `lock` chiama <xref:System.Threading.Monitor.Enter%2A> all'inizio del blocco e <xref:System.Threading.Monitor.Exit%2A> alla fine del blocco.</span><span class="sxs-lookup"><span data-stu-id="8f306-110">The `lock` keyword calls <xref:System.Threading.Monitor.Enter%2A> at the start of the block and <xref:System.Threading.Monitor.Exit%2A> at the end of the block.</span></span> <span data-ttu-id="8f306-111">Viene generata un'eccezione <xref:System.Threading.ThreadInterruptedException> se <xref:System.Threading.Thread.Interrupt%2A> interrompe un thread in attesa di immettere un'istruzione `lock`.</span><span class="sxs-lookup"><span data-stu-id="8f306-111">A <xref:System.Threading.ThreadInterruptedException> is thrown if <xref:System.Threading.Thread.Interrupt%2A> interrupts a thread that is waiting to enter a `lock` statement.</span></span>  
  
 <span data-ttu-id="8f306-112">In generale è opportuno evitare il blocco su un tipo `public` o su istanze oltre il controllo del codice.</span><span class="sxs-lookup"><span data-stu-id="8f306-112">In general, avoid locking on a `public` type, or instances beyond your code's control.</span></span> <span data-ttu-id="8f306-113">I costrutti comuni `lock (this)`, `lock (typeof (MyType))` e `lock ("myLock")` non rispettano questa regola:</span><span class="sxs-lookup"><span data-stu-id="8f306-113">The common constructs `lock (this)`, `lock (typeof (MyType))`, and `lock ("myLock")` violate this guideline:</span></span>  
  
-   <span data-ttu-id="8f306-114">`lock (this)` costituisce un problema se l'accesso all'istanza può avvenire pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="8f306-114">`lock (this)` is a problem if the instance can be accessed publicly.</span></span>  
  
-   <span data-ttu-id="8f306-115">`lock (typeof (MyType))` costituisce un problema se l'accesso a `MyType` può avvenire pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="8f306-115">`lock (typeof (MyType))` is a problem if `MyType` is publicly accessible.</span></span>  
  
-   <span data-ttu-id="8f306-116">`lock("myLock")` costituisce un problema poiché qualsiasi altro codice nel processo che usa la stessa stringa condividerà lo stesso blocco.</span><span class="sxs-lookup"><span data-stu-id="8f306-116">`lock("myLock")` is a problem because any other code in the process using the same string, will share the same lock.</span></span>  
  
 <span data-ttu-id="8f306-117">La procedura consigliata consiste nel definire un oggetto `private` da bloccare o una variabile oggetto `private static` per proteggere i dati comuni a tutte le istanze.</span><span class="sxs-lookup"><span data-stu-id="8f306-117">Best practice is to define a `private` object to lock on, or a `private static` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="8f306-118">Non è possibile usare la parola chiave [await](../../../csharp/language-reference/keywords/await.md) nel corpo di un'istruzione `lock`.</span><span class="sxs-lookup"><span data-stu-id="8f306-118">You can't use the [await](../../../csharp/language-reference/keywords/await.md) keyword in the body of a `lock` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f306-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f306-119">Example</span></span>  
 <span data-ttu-id="8f306-120">Nell'esempio seguente viene illustrato un uso semplificato dei thread senza blocco in C#.</span><span class="sxs-lookup"><span data-stu-id="8f306-120">The following sample shows a simple use of threads without locking in C#.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="8f306-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f306-121">Example</span></span>  
 <span data-ttu-id="8f306-122">Nell'esempio riportato di seguito vengono usati thread e `lock`.</span><span class="sxs-lookup"><span data-stu-id="8f306-122">The following sample uses threads and `lock`.</span></span> <span data-ttu-id="8f306-123">Finché è presente l'istruzione `lock`, il blocco di istruzioni rimarrà una sezione critica e `balance` non diventerà mai un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="8f306-123">As long as the `lock` statement is present, the statement block is a critical section and `balance` will never become a negative number.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8f306-124">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="8f306-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8f306-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f306-125">See Also</span></span>  
 <xref:System.Reflection.MethodImplAttributes>  
 <xref:System.Threading.Mutex>  
 [<span data-ttu-id="8f306-126">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="8f306-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8f306-127">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="8f306-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8f306-128">Threading</span><span class="sxs-lookup"><span data-stu-id="8f306-128">Threading</span></span>](../../programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="8f306-129">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="8f306-129">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8f306-130">Parole chiave per le istruzioni</span><span class="sxs-lookup"><span data-stu-id="8f306-130">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="8f306-131">Operazioni interlocked</span><span class="sxs-lookup"><span data-stu-id="8f306-131">Interlocked Operations</span></span>](../../../standard/threading/interlocked-operations.md)  
 [<span data-ttu-id="8f306-132">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="8f306-132">AutoResetEvent</span></span>](../../../standard/threading/autoresetevent.md)  
 [<span data-ttu-id="8f306-133">Sincronizzazione di thread</span><span class="sxs-lookup"><span data-stu-id="8f306-133">Thread Synchronization</span></span>](../../programming-guide/concepts/threading/thread-synchronization.md)
