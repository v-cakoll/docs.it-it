---
title: 'Procedura: eseguire codice di pulitura mediante finally (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
caps.latest.revision: 21
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
ms.openlocfilehash: b1f7bccacf20a9322f4de75740cdc34b4a97fa4c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a><span data-ttu-id="1a560-102">Procedura: eseguire codice di pulitura mediante finally (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="1a560-102">How to: Execute Cleanup Code Using finally (C# Programming Guide)</span></span>
<span data-ttu-id="1a560-103">Lo scopo di un'istruzione `finally` consiste nel garantire che la pulizia necessaria di oggetti, in genere oggetti che contengono risorse esterne, venga eseguita immediatamente, anche se viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1a560-103">The purpose of a `finally` statement is to ensure that the necessary cleanup of objects, usually objects that are holding external resources, occurs immediately, even if an exception is thrown.</span></span> <span data-ttu-id="1a560-104">Un esempio di questo tipo di pulizia è la chiamata di <xref:System.IO.Stream.Close%2A> in un oggetto <xref:System.IO.FileStream> immediatamente dopo l'uso, invece di aspettare che l'oggetto venga sottoposto a Garbage Collection da Common Language Runtime, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1a560-104">One example of such cleanup is calling <xref:System.IO.Stream.Close%2A> on a <xref:System.IO.FileStream> immediately after use instead of waiting for the object to be garbage collected by the common language runtime, as follows:</span></span>  
  
 <span data-ttu-id="1a560-105">[!code-cs[csProgGuideExceptions#16](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a560-105">[!code-cs[csProgGuideExceptions#16](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a560-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="1a560-106">Example</span></span>  
 <span data-ttu-id="1a560-107">Per trasformare il codice precedente in un'istruzione `try-catch-finally`, il codice di pulitura viene separato dal codice di lavoro, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="1a560-107">To turn the previous code into a `try-catch-finally` statement, the cleanup code is separated from the working code, as follows.</span></span>  
  
 <span data-ttu-id="1a560-108">[!code-cs[csProgGuideExceptions#17](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a560-108">[!code-cs[csProgGuideExceptions#17](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_2.cs)]</span></span>  
  
 <span data-ttu-id="1a560-109">Poiché può verificarsi un'eccezione in qualsiasi momento all'interno del blocco `try` prima della chiamata a `OpenWrite()`, oppure la chiamata a `OpenWrite()` stessa potrebbe non riuscire, non esiste alcuna garanzia che il file sia aperto quando si tenta di chiuderlo.</span><span class="sxs-lookup"><span data-stu-id="1a560-109">Because an exception can occur at any time within the `try` block before the `OpenWrite()` call, or the `OpenWrite()` call itself could fail, we are not guaranteed that the file is open when we try to close it.</span></span> <span data-ttu-id="1a560-110">Il blocco `finally` aggiunge un controllo per verificare che l'oggetto <xref:System.IO.FileStream> non sia `null` prima di chiamare il metodo <xref:System.IO.Stream.Close%2A>.</span><span class="sxs-lookup"><span data-stu-id="1a560-110">The `finally` block adds a check to make sure that the <xref:System.IO.FileStream> object is not `null` before you call the <xref:System.IO.Stream.Close%2A> method.</span></span> <span data-ttu-id="1a560-111">Senza il controllo di `null`, il blocco `finally` potrebbe generare la propria eccezione <xref:System.NullReferenceException>, ma la generazione di eccezioni nei blocchi `finally` deve essere evitata, se possibile.</span><span class="sxs-lookup"><span data-stu-id="1a560-111">Without the `null` check, the `finally` block could throw its own <xref:System.NullReferenceException>, but throwing exceptions in `finally` blocks should be avoided if it is possible.</span></span>  
  
 <span data-ttu-id="1a560-112">Una connessione di database è un altro elemento ideale da chiudere in un blocco `finally`.</span><span class="sxs-lookup"><span data-stu-id="1a560-112">A database connection is another good candidate for being closed in a `finally` block.</span></span> <span data-ttu-id="1a560-113">Poiché il numero di connessioni consentite in un server di database è talvolta limitato, è necessario chiudere le connessioni di database il più rapidamente possibile.</span><span class="sxs-lookup"><span data-stu-id="1a560-113">Because the number of connections allowed to a database server is sometimes limited, you should close database connections as quickly as possible.</span></span> <span data-ttu-id="1a560-114">Se viene generata un'eccezione prima che la connessione venga chiusa, l'uso del blocco `finally` è preferibile rispetto all'attesa di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1a560-114">If an exception is thrown before you can close your connection, this is another case where using the `finally` block is better than waiting for garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a560-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a560-115">See Also</span></span>  
 <span data-ttu-id="1a560-116">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a560-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1a560-117">[Eccezioni e gestione delle eccezioni](../../../csharp/programming-guide/exceptions/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a560-117">[Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md) </span></span>  
 <span data-ttu-id="1a560-118">[Gestione delle eccezioni](../../../csharp/programming-guide/exceptions/exception-handling.md) </span><span class="sxs-lookup"><span data-stu-id="1a560-118">[Exception Handling](../../../csharp/programming-guide/exceptions/exception-handling.md) </span></span>  
 <span data-ttu-id="1a560-119">[Istruzione using](../../../csharp/language-reference/keywords/using-statement.md) </span><span class="sxs-lookup"><span data-stu-id="1a560-119">[using Statement](../../../csharp/language-reference/keywords/using-statement.md) </span></span>  
 <span data-ttu-id="1a560-120">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="1a560-120">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="1a560-121">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span><span class="sxs-lookup"><span data-stu-id="1a560-121">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span></span>  
 [<span data-ttu-id="1a560-122">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="1a560-122">try-catch-finally</span></span>](../../../csharp/language-reference/keywords/try-catch-finally.md)

