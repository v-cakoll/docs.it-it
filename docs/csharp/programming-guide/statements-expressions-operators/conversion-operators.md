---
title: Operatori di conversione (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c12fd13d6526d79363f973ce2a944c4823bf4104
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="8da2a-102">Operatori di conversione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="8da2a-102">Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="8da2a-103">C# consente ai programmatori di dichiarare conversioni in classi o struct, in modo che sia possibile convertire le classi o gli struct da e/o in altre classi o altri struct oppure tipi di base.</span><span class="sxs-lookup"><span data-stu-id="8da2a-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="8da2a-104">Le conversioni vengono definite come operatori e sono denominate in base al tipo di destinazione della conversione.</span><span class="sxs-lookup"><span data-stu-id="8da2a-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="8da2a-105">Il tipo dell'argomento da convertire oppure il tipo del risultato della conversione, ma non entrambi, deve essere il tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="8da2a-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 <span data-ttu-id="8da2a-106">[!code-cs[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8da2a-106">[!code-cs[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]</span></span>  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="8da2a-107">Panoramica degli operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="8da2a-107">Conversion Operators Overview</span></span>  
 <span data-ttu-id="8da2a-108">Gli operatori di conversione hanno le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="8da2a-108">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="8da2a-109">Le conversioni dichiarate come `implicit` vengono eseguite automaticamente quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="8da2a-109">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="8da2a-110">Le conversioni dichiarate come `explicit` richiedono che venga chiamato un cast.</span><span class="sxs-lookup"><span data-stu-id="8da2a-110">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="8da2a-111">Tutte le conversioni devono essere dichiarate come `static`.</span><span class="sxs-lookup"><span data-stu-id="8da2a-111">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8da2a-112">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="8da2a-112">Related Sections</span></span>  
 <span data-ttu-id="8da2a-113">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="8da2a-113">For more information:</span></span>  
  
-   [<span data-ttu-id="8da2a-114">Uso degli operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="8da2a-114">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="8da2a-115">Cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="8da2a-115">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="8da2a-116">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="8da2a-116">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="8da2a-117">explicit</span><span class="sxs-lookup"><span data-stu-id="8da2a-117">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="8da2a-118">implicit</span><span class="sxs-lookup"><span data-stu-id="8da2a-118">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="8da2a-119">static</span><span class="sxs-lookup"><span data-stu-id="8da2a-119">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="8da2a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8da2a-120">See Also</span></span>  
 <span data-ttu-id="8da2a-121"><xref:System.Convert></span><span class="sxs-lookup"><span data-stu-id="8da2a-121"><xref:System.Convert></span></span>   
 <span data-ttu-id="8da2a-122">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8da2a-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="8da2a-123">Conversioni esplicite concatenate definite dall'utente in C#</span><span class="sxs-lookup"><span data-stu-id="8da2a-123">Chained user-defined explicit conversions in C#</span></span>](http://go.microsoft.com/fwlink/?LinkId=112384)

