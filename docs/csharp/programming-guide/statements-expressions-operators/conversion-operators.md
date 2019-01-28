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
ms.openlocfilehash: 071eb75d9bab2b91b9cdb8ecc33df249b01e7ac6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619762"
---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="f5ff4-102">Operatori di conversione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="f5ff4-102">Conversion operators (C# Programming Guide)</span></span>

<span data-ttu-id="f5ff4-103">C# consente ai programmatori di dichiarare conversioni in classi o struct, in modo che sia possibile convertire le classi o gli struct da e/o in altre classi o altri struct oppure tipi di base.</span><span class="sxs-lookup"><span data-stu-id="f5ff4-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="f5ff4-104">Le conversioni vengono definite come operatori e sono denominate in base al tipo di destinazione della conversione.</span><span class="sxs-lookup"><span data-stu-id="f5ff4-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="f5ff4-105">Il tipo dell'argomento da convertire oppure il tipo del risultato della conversione, ma non entrambi, deve essere il tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="f5ff4-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="f5ff4-106">Panoramica degli operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="f5ff4-106">Conversion operators overview</span></span>

 <span data-ttu-id="f5ff4-107">Gli operatori di conversione hanno le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5ff4-107">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="f5ff4-108">Le conversioni dichiarate come `implicit` vengono eseguite automaticamente quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="f5ff4-108">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="f5ff4-109">Le conversioni dichiarate come `explicit` richiedono che venga chiamato un cast.</span><span class="sxs-lookup"><span data-stu-id="f5ff4-109">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="f5ff4-110">Tutte le conversioni devono essere dichiarate come `static`.</span><span class="sxs-lookup"><span data-stu-id="f5ff4-110">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f5ff4-111">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="f5ff4-111">Related sections</span></span>

 <span data-ttu-id="f5ff4-112">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="f5ff4-112">For more information:</span></span>  
  
-   [<span data-ttu-id="f5ff4-113">Uso degli operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="f5ff4-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="f5ff4-114">Cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="f5ff4-114">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="f5ff4-115">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="f5ff4-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="f5ff4-116">explicit</span><span class="sxs-lookup"><span data-stu-id="f5ff4-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="f5ff4-117">implicit</span><span class="sxs-lookup"><span data-stu-id="f5ff4-117">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="f5ff4-118">static</span><span class="sxs-lookup"><span data-stu-id="f5ff4-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="f5ff4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5ff4-119">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="f5ff4-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f5ff4-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f5ff4-121">Conversioni esplicite concatenate definite dall'utente in C#</span><span class="sxs-lookup"><span data-stu-id="f5ff4-121">Chained user-defined explicit conversions in C#</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
