---
title: Istruzioni, espressioni e operatori (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- expressions [C#]
- operators [C#]
- C# language, statements
- C# language, operators
- C# language, expressions
- statements [C#]
ms.assetid: 20f8469d-5a6a-4084-ad90-0856b7e97e45
caps.latest.revision: 22
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
ms.openlocfilehash: 71988a5b9aa59b2655b4fd7b91522fe69c8064b6
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="statements-expressions-and-operators-c-programming-guide"></a><span data-ttu-id="0abd8-102">Istruzioni, espressioni e operatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="0abd8-102">Statements, Expressions, and Operators (C# Programming Guide)</span></span>
<span data-ttu-id="0abd8-103">Il codice C# di un'applicazione è costituito da istruzioni che contengono parole chiave, espressioni e operatori.</span><span class="sxs-lookup"><span data-stu-id="0abd8-103">The C# code that comprises an application consists of statements made up of keywords, expressions and operators.</span></span> <span data-ttu-id="0abd8-104">Questa sezione contiene informazioni relative a tali elementi fondamentali di un programma C#.</span><span class="sxs-lookup"><span data-stu-id="0abd8-104">This section contains information regarding these fundamental elements of a C# program.</span></span>  
  
 <span data-ttu-id="0abd8-105">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="0abd8-105">For more information, see:</span></span>  
  
-   [<span data-ttu-id="0abd8-106">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="0abd8-106">Statements</span></span>](../../../csharp/programming-guide/statements-expressions-operators/statements.md)  
  
-   [<span data-ttu-id="0abd8-107">Espressioni</span><span class="sxs-lookup"><span data-stu-id="0abd8-107">Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
    -   [<span data-ttu-id="0abd8-108">Membri con corpo di espressione</span><span class="sxs-lookup"><span data-stu-id="0abd8-108">Expression-bodied members</span></span>](expression-bodied-members.md)
 
-   [<span data-ttu-id="0abd8-109">Operatori</span><span class="sxs-lookup"><span data-stu-id="0abd8-109">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
-   [<span data-ttu-id="0abd8-110">Funzioni anonime</span><span class="sxs-lookup"><span data-stu-id="0abd8-110">Anonymous Functions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [<span data-ttu-id="0abd8-111">Operatori che supportano l'overload</span><span class="sxs-lookup"><span data-stu-id="0abd8-111">Overloadable Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)  
  
-   [<span data-ttu-id="0abd8-112">Operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="0abd8-112">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
  
    -   [<span data-ttu-id="0abd8-113">Uso degli operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="0abd8-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
    -   [<span data-ttu-id="0abd8-114">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="0abd8-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="0abd8-115">Procedura: Usare l'overload degli operatori per creare una classe di numeri complessi</span><span class="sxs-lookup"><span data-stu-id="0abd8-115">How to: Use Operator Overloading to Create a Complex Number Class</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md)  
  
-   [<span data-ttu-id="0abd8-116">Confronti di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="0abd8-116">Equality Comparisons</span></span>](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="0abd8-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0abd8-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0abd8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0abd8-118">See Also</span></span>  
 <span data-ttu-id="0abd8-119">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0abd8-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="0abd8-120">Cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="0abd8-120">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)

