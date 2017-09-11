---
title: Istruzione lock (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- lock_CSharpKeyword
- lock
dev_langs:
- CSharp
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 00dcbb9feec11587265bf61667d91c2c1598065b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="f8088-102">Istruzione lock (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f8088-102">lock Statement (C# Reference)</span></span>
<span data-ttu-id="f8088-103">La parola chiave `lock` contrassegna un blocco di istruzioni come sezione critica ottenendo il blocco a esclusione reciproca per un determinato oggetto, eseguendo un'istruzione e rilasciando in seguito il blocco.</span><span class="sxs-lookup"><span data-stu-id="f8088-103">The `lock` keyword marks a statement block as a critical section by obtaining the mutual-exclusion lock for a given object, executing a statement, and then releasing the lock.</span></span> <span data-ttu-id="f8088-104">L'esempio seguente illustra un'istruzione `lock`.</span><span class="sxs-lookup"><span data-stu-id="f8088-104">The following example includes a `lock` statement.</span></span>  
  
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
  
 <span data-ttu-id="f8088-105">Per altre informazioni, vedere [Sincronizzazione di thread](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4).</span><span class="sxs-lookup"><span data-stu-id="f8088-105">For more information, see [Thread Synchronization](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8088-106">Note</span><span class="sxs-lookup"><span data-stu-id="f8088-106">Remarks</span></span>  
 <span data-ttu-id="f8088-107">La parola chiave `lock` impedisce a un thread di entrare in una sezione critica del codice se è già presente un altro thread.</span><span class="sxs-lookup"><span data-stu-id="f8088-107">The `lock` keyword ensures that one thread does not enter a critical section of code while another thread is in the critical section.</span></span> <span data-ttu-id="f8088-108">Se un altro thread tenta di accedere a un codice bloccato, attenderà (in stato di blocco) finché l'oggetto non verrà rilasciato.</span><span class="sxs-lookup"><span data-stu-id="f8088-108">If another thread tries to enter a locked code, it will wait, block, until the object is released.</span></span>  
  
 <span data-ttu-id="f8088-109">Nella sezione [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) vengono specificate informazioni sul threading.</span><span class="sxs-lookup"><span data-stu-id="f8088-109">The section [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) discusses threading.</span></span>  
  
 <span data-ttu-id="f8088-110">La parola chiave `lock` chiama <xref:System.Threading.Monitor.Enter%2A> all'inizio del blocco e <xref:System.Threading.Monitor.Exit%2A> alla fine del blocco.</span><span class="sxs-lookup"><span data-stu-id="f8088-110">The `lock` keyword calls <xref:System.Threading.Monitor.Enter%2A> at the start of the block and <xref:System.Threading.Monitor.Exit%2A> at the end of the block.</span></span> <span data-ttu-id="f8088-111">Viene generata un'eccezione <xref:System.Threading.ThreadInterruptedException> se <xref:System.Threading.Thread.Interrupt%2A> interrompe un thread in attesa di immettere un'istruzione `lock`.</span><span class="sxs-lookup"><span data-stu-id="f8088-111">A <xref:System.Threading.ThreadInterruptedException> is thrown if <xref:System.Threading.Thread.Interrupt%2A> interrupts a thread that is waiting to enter a `lock` statement.</span></span>  
  
 <span data-ttu-id="f8088-112">In generale è opportuno evitare il blocco su un tipo `public` o su istanze oltre il controllo del codice.</span><span class="sxs-lookup"><span data-stu-id="f8088-112">In general, avoid locking on a `public` type, or instances beyond your code's control.</span></span> <span data-ttu-id="f8088-113">I costrutti comuni `lock (this)`, `lock (typeof (MyType))` e `lock ("myLock")` non rispettano questa regola:</span><span class="sxs-lookup"><span data-stu-id="f8088-113">The common constructs `lock (this)`, `lock (typeof (MyType))`, and `lock ("myLock")` violate this guideline:</span></span>  
  
-   <span data-ttu-id="f8088-114">`lock (this)` costituisce un problema se l'accesso all'istanza può avvenire pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="f8088-114">`lock (this)` is a problem if the instance can be accessed publicly.</span></span>  
  
-   <span data-ttu-id="f8088-115">`lock (typeof (MyType))` costituisce un problema se l'accesso a `MyType` può avvenire pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="f8088-115">`lock (typeof (MyType))` is a problem if `MyType` is publicly accessible.</span></span>  
  
-   <span data-ttu-id="f8088-116">`lock("myLock")` costituisce un problema poiché qualsiasi altro codice nel processo che usa la stessa stringa condividerà lo stesso blocco.</span><span class="sxs-lookup"><span data-stu-id="f8088-116">`lock("myLock")` is a problem because any other code in the process using the same string, will share the same lock.</span></span>  
  
 <span data-ttu-id="f8088-117">La procedura consigliata consiste nel definire un oggetto `private` da bloccare o una variabile oggetto `private static` per proteggere i dati comuni a tutte le istanze.</span><span class="sxs-lookup"><span data-stu-id="f8088-117">Best practice is to define a `private` object to lock on, or a `private static` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="f8088-118">Non è possibile usare la parola chiave [await](../../../csharp/language-reference/keywords/await.md) nel corpo di un'istruzione `lock`.</span><span class="sxs-lookup"><span data-stu-id="f8088-118">You can't use the [await](../../../csharp/language-reference/keywords/await.md) keyword in the body of a `lock` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8088-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8088-119">Example</span></span>  
 <span data-ttu-id="f8088-120">Nell'esempio seguente viene illustrato un uso semplificato dei thread senza blocco in C#.</span><span class="sxs-lookup"><span data-stu-id="f8088-120">The following sample shows a simple use of threads without locking in C#.</span></span>  
  
 <span data-ttu-id="f8088-121">[!code-cs[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8088-121">[!code-cs[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8088-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8088-122">Example</span></span>  
 <span data-ttu-id="f8088-123">Nell'esempio riportato di seguito vengono usati thread e `lock`.</span><span class="sxs-lookup"><span data-stu-id="f8088-123">The following sample uses threads and `lock`.</span></span> <span data-ttu-id="f8088-124">Finché è presente l'istruzione `lock`, il blocco di istruzioni rimarrà una sezione critica e `balance` non diventerà mai un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="f8088-124">As long as the `lock` statement is present, the statement block is a critical section and `balance` will never become a negative number.</span></span>  
  
 <span data-ttu-id="f8088-125">[!code-cs[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8088-125">[!code-cs[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f8088-126">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="f8088-126">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f8088-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8088-127">See Also</span></span>  
 <span data-ttu-id="f8088-128"><xref:System.Reflection.MethodImplAttributes></span><span class="sxs-lookup"><span data-stu-id="f8088-128"><xref:System.Reflection.MethodImplAttributes></span></span>   
 <span data-ttu-id="f8088-129"><xref:System.Threading.Mutex></span><span class="sxs-lookup"><span data-stu-id="f8088-129"><xref:System.Threading.Mutex></span></span>   
 <span data-ttu-id="f8088-130">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f8088-130">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f8088-131">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f8088-131">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f8088-132">[Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) </span><span class="sxs-lookup"><span data-stu-id="f8088-132">[Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) </span></span>  
 <span data-ttu-id="f8088-133">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f8088-133">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="f8088-134">[Parole chiave per le istruzioni](../../../csharp/language-reference/keywords/statement-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="f8088-134">[Statement Keywords](../../../csharp/language-reference/keywords/statement-keywords.md) </span></span>  
 <span data-ttu-id="f8088-135">@System.Threading.Monitor</span><span class="sxs-lookup"><span data-stu-id="f8088-135">@System.Threading.Monitor</span></span>   
 <span data-ttu-id="f8088-136">[Operazioni interlocked](../../../standard/threading/interlocked-operations.md) </span><span class="sxs-lookup"><span data-stu-id="f8088-136">[Interlocked Operations](../../../standard/threading/interlocked-operations.md) </span></span>  
 <span data-ttu-id="f8088-137">[AutoResetEvent](../../../standard/threading/autoresetevent.md) </span><span class="sxs-lookup"><span data-stu-id="f8088-137">[AutoResetEvent](../../../standard/threading/autoresetevent.md) </span></span>  
 [<span data-ttu-id="f8088-138">Sincronizzazione di thread</span><span class="sxs-lookup"><span data-stu-id="f8088-138">Thread Synchronization</span></span>](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4)

