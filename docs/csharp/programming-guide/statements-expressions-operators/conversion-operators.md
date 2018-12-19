---
title: Operatori di conversione - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
ms.openlocfilehash: a55a2148ce161deca79d8ba8e64a217e474f0284
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236817"
---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="05295-102">Operatori di conversione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="05295-102">Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="05295-103">C# consente ai programmatori di dichiarare conversioni in classi o struct, in modo che sia possibile convertire le classi o gli struct da e/o in altre classi o altri struct oppure tipi di base.</span><span class="sxs-lookup"><span data-stu-id="05295-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="05295-104">Le conversioni vengono definite come operatori e sono denominate in base al tipo di destinazione della conversione.</span><span class="sxs-lookup"><span data-stu-id="05295-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="05295-105">Il tipo dell'argomento da convertire oppure il tipo del risultato della conversione, ma non entrambi, deve essere il tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="05295-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="05295-106">Panoramica degli operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="05295-106">Conversion Operators Overview</span></span>  
 <span data-ttu-id="05295-107">Gli operatori di conversione hanno le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="05295-107">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="05295-108">Le conversioni dichiarate come `implicit` vengono eseguite automaticamente quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="05295-108">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="05295-109">Le conversioni dichiarate come `explicit` richiedono che venga chiamato un cast.</span><span class="sxs-lookup"><span data-stu-id="05295-109">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="05295-110">Tutte le conversioni devono essere dichiarate come `static`.</span><span class="sxs-lookup"><span data-stu-id="05295-110">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="05295-111">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="05295-111">Related Sections</span></span>  
 <span data-ttu-id="05295-112">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="05295-112">For more information:</span></span>  
  
-   [<span data-ttu-id="05295-113">Uso degli operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="05295-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="05295-114">Cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="05295-114">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="05295-115">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="05295-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="05295-116">explicit</span><span class="sxs-lookup"><span data-stu-id="05295-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="05295-117">implicit</span><span class="sxs-lookup"><span data-stu-id="05295-117">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="05295-118">static</span><span class="sxs-lookup"><span data-stu-id="05295-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="05295-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05295-119">See Also</span></span>

- <xref:System.Convert>  
- [<span data-ttu-id="05295-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="05295-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="05295-121">Conversioni esplicite concatenate definite dall'utente in C#</span><span class="sxs-lookup"><span data-stu-id="05295-121">Chained user-defined explicit conversions in C#</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
