---
title: Operatori di conversione (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5277c1160c604ee56ff575df5bd603e115588d21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="c1497-102">Operatori di conversione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="c1497-102">Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="c1497-103">C# consente ai programmatori di dichiarare conversioni in classi o struct, in modo che sia possibile convertire le classi o gli struct da e/o in altre classi o altri struct oppure tipi di base.</span><span class="sxs-lookup"><span data-stu-id="c1497-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="c1497-104">Le conversioni vengono definite come operatori e sono denominate in base al tipo di destinazione della conversione.</span><span class="sxs-lookup"><span data-stu-id="c1497-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="c1497-105">Il tipo dell'argomento da convertire oppure il tipo del risultato della conversione, ma non entrambi, deve essere il tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="c1497-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="c1497-106">Panoramica degli operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="c1497-106">Conversion Operators Overview</span></span>  
 <span data-ttu-id="c1497-107">Gli operatori di conversione hanno le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1497-107">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="c1497-108">Le conversioni dichiarate come `implicit` vengono eseguite automaticamente quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="c1497-108">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="c1497-109">Le conversioni dichiarate come `explicit` richiedono che venga chiamato un cast.</span><span class="sxs-lookup"><span data-stu-id="c1497-109">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="c1497-110">Tutte le conversioni devono essere dichiarate come `static`.</span><span class="sxs-lookup"><span data-stu-id="c1497-110">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c1497-111">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c1497-111">Related Sections</span></span>  
 <span data-ttu-id="c1497-112">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="c1497-112">For more information:</span></span>  
  
-   [<span data-ttu-id="c1497-113">Uso degli operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="c1497-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="c1497-114">Cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="c1497-114">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="c1497-115">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="c1497-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="c1497-116">explicit</span><span class="sxs-lookup"><span data-stu-id="c1497-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="c1497-117">implicit</span><span class="sxs-lookup"><span data-stu-id="c1497-117">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="c1497-118">static</span><span class="sxs-lookup"><span data-stu-id="c1497-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="c1497-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1497-119">See Also</span></span>  
 <xref:System.Convert>  
 [<span data-ttu-id="c1497-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c1497-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c1497-121">Conversioni esplicite concatenate definite dall'utente in C#</span><span class="sxs-lookup"><span data-stu-id="c1497-121">Chained user-defined explicit conversions in C#</span></span>](http://go.microsoft.com/fwlink/?LinkId=112384)
