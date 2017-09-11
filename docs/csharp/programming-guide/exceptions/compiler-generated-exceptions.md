---
title: Eccezioni generate dal compilatore (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
caps.latest.revision: 13
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
ms.openlocfilehash: d8fbae9272b34dd4d010199470c930c846cd1b74
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="compiler-generated-exceptions-c-programming-guide"></a><span data-ttu-id="625d2-102">Eccezioni generate dal compilatore (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="625d2-102">Compiler-Generated Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="625d2-103">Alcune eccezioni vengono generate automaticamente da Common Language Runtime (CLR) di .NET Framework quando le operazioni di base hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="625d2-103">Some exceptions are thrown automatically by the .NET Framework's common language runtime (CLR) when basic operations fail.</span></span> <span data-ttu-id="625d2-104">Nella tabella seguente sono elencate queste eccezioni e le relative condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="625d2-104">These exceptions and their error conditions are listed in the following table.</span></span>  
  
|<span data-ttu-id="625d2-105">Eccezione</span><span class="sxs-lookup"><span data-stu-id="625d2-105">Exception</span></span>|<span data-ttu-id="625d2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="625d2-106">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|<span data-ttu-id="625d2-107">Classe di base per le eccezioni che si verificano durante operazioni aritmetiche, quali <xref:System.DivideByZeroException> e <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="625d2-107">A base class for exceptions that occur during arithmetic operations, such as <xref:System.DivideByZeroException> and <xref:System.OverflowException>.</span></span>|  
|<xref:System.ArrayTypeMismatchException>|<span data-ttu-id="625d2-108">Generata quando una matrice non può archiviare un determinato elemento perché il tipo effettivo dell'elemento non è compatibile con il tipo effettivo della matrice.</span><span class="sxs-lookup"><span data-stu-id="625d2-108">Thrown when an array cannot store a given element because the actual type of the element is incompatible with the actual type of the array.</span></span>|  
|<xref:System.DivideByZeroException>|<span data-ttu-id="625d2-109">Generata quando viene eseguito un tentativo di dividere un valore integrale per zero.</span><span class="sxs-lookup"><span data-stu-id="625d2-109">Thrown when an attempt is made to divide an integral value by zero.</span></span>|  
|<xref:System.IndexOutOfRangeException>|<span data-ttu-id="625d2-110">Generata quando viene eseguito un tentativo di indicizzare una matrice, quando l'indice è minore di zero o supera i limiti della matrice.</span><span class="sxs-lookup"><span data-stu-id="625d2-110">Thrown when an attempt is made to index an array when the index is less than zero or outside the bounds of the array.</span></span>|  
|<xref:System.InvalidCastException>|<span data-ttu-id="625d2-111">Generata quando una conversione esplicita dal tipo di base a un'interfaccia o a un tipo derivato ha esito negativo in fase di runtime.</span><span class="sxs-lookup"><span data-stu-id="625d2-111">Thrown when an explicit conversion from a base type to an interface or to a derived type fails at runtime.</span></span>|  
|<xref:System.NullReferenceException>|<span data-ttu-id="625d2-112">Generata quando si tenta di fare riferimento a un oggetto il cui valore è [null](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="625d2-112">Thrown when you attempt to reference an object whose value is [null](../../../csharp/language-reference/keywords/null.md).</span></span>|  
|<xref:System.OutOfMemoryException>|<span data-ttu-id="625d2-113">Generata quando un tentativo di allocazione della memoria tramite l'operatore [new](../../../csharp/language-reference/keywords/new-operator.md) ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="625d2-113">Thrown when an attempt to allocate memory using the [new](../../../csharp/language-reference/keywords/new-operator.md) operator fails.</span></span> <span data-ttu-id="625d2-114">Ciò indica che è stata esaurita la memoria disponibile per Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="625d2-114">This indicates that the memory available to the common language runtime has been exhausted.</span></span>|  
|<xref:System.OverflowException>|<span data-ttu-id="625d2-115">Generata quando si verifica un overflow di un'operazione aritmetica in un contesto `checked`.</span><span class="sxs-lookup"><span data-stu-id="625d2-115">Thrown when an arithmetic operation in a `checked` context overflows.</span></span>|  
|<xref:System.StackOverflowException>|<span data-ttu-id="625d2-116">Generata quando viene esaurito lo stack di esecuzione da un numero eccessivo di chiamate in sospeso verso il metodo; in genere indica un problema di ricorsione molto profondo o infinito.</span><span class="sxs-lookup"><span data-stu-id="625d2-116">Thrown when the execution stack is exhausted by having too many pending method calls; usually indicates a very deep or infinite recursion.</span></span>|  
|<xref:System.TypeInitializationException>|<span data-ttu-id="625d2-117">Generata quando un costruttore statico genera un'eccezione e non è presente una clausola `catch` compatibile per intercettarla.</span><span class="sxs-lookup"><span data-stu-id="625d2-117">Thrown when a static constructor throws an exception and no compatible `catch` clause exists to catch it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="625d2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="625d2-118">See Also</span></span>  
 <span data-ttu-id="625d2-119">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="625d2-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="625d2-120">[Eccezioni e gestione delle eccezioni](../../../csharp/programming-guide/exceptions/index.md) </span><span class="sxs-lookup"><span data-stu-id="625d2-120">[Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md) </span></span>  
 <span data-ttu-id="625d2-121">[Gestione delle eccezioni](../../../csharp/programming-guide/exceptions/exception-handling.md) </span><span class="sxs-lookup"><span data-stu-id="625d2-121">[Exception Handling](../../../csharp/programming-guide/exceptions/exception-handling.md) </span></span>  
 <span data-ttu-id="625d2-122">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="625d2-122">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="625d2-123">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span><span class="sxs-lookup"><span data-stu-id="625d2-123">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span></span>  
 [<span data-ttu-id="625d2-124">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="625d2-124">try-catch-finally</span></span>](../../../csharp/language-reference/keywords/try-catch-finally.md)

