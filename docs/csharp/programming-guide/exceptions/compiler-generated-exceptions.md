---
title: Eccezioni generate dal compilatore - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: e21b75e5b7e338bda54ca00abaa733775865fdb9
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238390"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a><span data-ttu-id="aefe4-102">Eccezioni generate dal compilatore (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="aefe4-102">Compiler-Generated Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="aefe4-103">Alcune eccezioni vengono generate automaticamente da Common Language Runtime (CLR) di .NET Framework quando le operazioni di base hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="aefe4-103">Some exceptions are thrown automatically by the .NET Framework's common language runtime (CLR) when basic operations fail.</span></span> <span data-ttu-id="aefe4-104">Nella tabella seguente sono elencate queste eccezioni e le relative condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="aefe4-104">These exceptions and their error conditions are listed in the following table.</span></span>  
  
|<span data-ttu-id="aefe4-105">Eccezione</span><span class="sxs-lookup"><span data-stu-id="aefe4-105">Exception</span></span>|<span data-ttu-id="aefe4-106">Description</span><span class="sxs-lookup"><span data-stu-id="aefe4-106">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|<span data-ttu-id="aefe4-107">Classe di base per le eccezioni che si verificano durante operazioni aritmetiche, quali <xref:System.DivideByZeroException> e <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="aefe4-107">A base class for exceptions that occur during arithmetic operations, such as <xref:System.DivideByZeroException> and <xref:System.OverflowException>.</span></span>|  
|<xref:System.ArrayTypeMismatchException>|<span data-ttu-id="aefe4-108">Generata quando una matrice non può archiviare un determinato elemento perché il tipo effettivo dell'elemento non è compatibile con il tipo effettivo della matrice.</span><span class="sxs-lookup"><span data-stu-id="aefe4-108">Thrown when an array cannot store a given element because the actual type of the element is incompatible with the actual type of the array.</span></span>|  
|<xref:System.DivideByZeroException>|<span data-ttu-id="aefe4-109">Generata quando viene eseguito un tentativo di dividere un valore integrale per zero.</span><span class="sxs-lookup"><span data-stu-id="aefe4-109">Thrown when an attempt is made to divide an integral value by zero.</span></span>|  
|<xref:System.IndexOutOfRangeException>|<span data-ttu-id="aefe4-110">Generata quando viene eseguito un tentativo di indicizzare una matrice, quando l'indice è minore di zero o supera i limiti della matrice.</span><span class="sxs-lookup"><span data-stu-id="aefe4-110">Thrown when an attempt is made to index an array when the index is less than zero or outside the bounds of the array.</span></span>|  
|<xref:System.InvalidCastException>|<span data-ttu-id="aefe4-111">Generata quando una conversione esplicita dal tipo di base a un'interfaccia o a un tipo derivato ha esito negativo in fase di runtime.</span><span class="sxs-lookup"><span data-stu-id="aefe4-111">Thrown when an explicit conversion from a base type to an interface or to a derived type fails at runtime.</span></span>|  
|<xref:System.NullReferenceException>|<span data-ttu-id="aefe4-112">Generata quando si tenta di fare riferimento a un oggetto il cui valore è [null](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="aefe4-112">Thrown when you attempt to reference an object whose value is [null](../../../csharp/language-reference/keywords/null.md).</span></span>|  
|<xref:System.OutOfMemoryException>|<span data-ttu-id="aefe4-113">Generata quando un tentativo di allocazione della memoria tramite l'operatore [new](../../../csharp/language-reference/keywords/new-operator.md) ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="aefe4-113">Thrown when an attempt to allocate memory using the [new](../../../csharp/language-reference/keywords/new-operator.md) operator fails.</span></span> <span data-ttu-id="aefe4-114">Ciò indica che è stata esaurita la memoria disponibile per Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="aefe4-114">This indicates that the memory available to the common language runtime has been exhausted.</span></span>|  
|<xref:System.OverflowException>|<span data-ttu-id="aefe4-115">Generata quando si verifica un overflow di un'operazione aritmetica in un contesto `checked`.</span><span class="sxs-lookup"><span data-stu-id="aefe4-115">Thrown when an arithmetic operation in a `checked` context overflows.</span></span>|  
|<xref:System.StackOverflowException>|<span data-ttu-id="aefe4-116">Generata quando viene esaurito lo stack di esecuzione da un numero eccessivo di chiamate in sospeso verso il metodo; in genere indica un problema di ricorsione molto profondo o infinito.</span><span class="sxs-lookup"><span data-stu-id="aefe4-116">Thrown when the execution stack is exhausted by having too many pending method calls; usually indicates a very deep or infinite recursion.</span></span>|  
|<xref:System.TypeInitializationException>|<span data-ttu-id="aefe4-117">Generata quando un costruttore statico genera un'eccezione e non è presente una clausola `catch` compatibile per intercettarla.</span><span class="sxs-lookup"><span data-stu-id="aefe4-117">Thrown when a static constructor throws an exception and no compatible `catch` clause exists to catch it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aefe4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aefe4-118">See Also</span></span>

- [<span data-ttu-id="aefe4-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="aefe4-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="aefe4-120">Eccezioni e gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="aefe4-120">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)  
- [<span data-ttu-id="aefe4-121">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="aefe4-121">Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/exception-handling.md)  
- [<span data-ttu-id="aefe4-122">try-catch</span><span class="sxs-lookup"><span data-stu-id="aefe4-122">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
- [<span data-ttu-id="aefe4-123">try-finally</span><span class="sxs-lookup"><span data-stu-id="aefe4-123">try-finally</span></span>](../../../csharp/language-reference/keywords/try-finally.md)  
- [<span data-ttu-id="aefe4-124">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="aefe4-124">try-catch-finally</span></span>](../../../csharp/language-reference/keywords/try-catch-finally.md)
