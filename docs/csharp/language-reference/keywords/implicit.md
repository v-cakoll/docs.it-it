---
title: implicit (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c893c7a9afbdc6f715010d537e9ccaf66c5785c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-c-reference"></a><span data-ttu-id="ffe2c-102">implicit (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="ffe2c-102">implicit (C# Reference)</span></span>
<span data-ttu-id="ffe2c-103">La parola chiave `implicit` viene usata per dichiarare un operatore di conversione implicita di tipi definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ffe2c-103">The `implicit` keyword is used to declare an implicit user-defined type conversion operator.</span></span> <span data-ttu-id="ffe2c-104">È possibile usare questa parola chiave per abilitare le conversioni implicite tra un tipo definito dall'utente e un altro tipo, se è garantito che tale conversione non provoca una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="ffe2c-104">Use it to enable implicit conversions between a user-defined type and another type, if the conversion is guaranteed not to cause a loss of data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffe2c-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="ffe2c-105">Example</span></span>  
 [!code-csharp[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]  
  
 <span data-ttu-id="ffe2c-106">Grazie all'eliminazione dei cast non necessari, le conversioni implicite contribuiscono a migliorare la leggibilità del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="ffe2c-106">By eliminating unnecessary casts, implicit conversions can improve source code readability.</span></span> <span data-ttu-id="ffe2c-107">Tuttavia, poiché per le conversioni implicite non è necessario eseguire il cast in modo esplicito da un tipo all'altro, è importante assicurarsi di non ottenere risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="ffe2c-107">However, because implicit conversions do not require programmers to explicitly cast from one type to the other, care must be taken to prevent unexpected results.</span></span> <span data-ttu-id="ffe2c-108">In genere, per poter essere usati in modo sicuro senza il controllo del programmatore, gli operatori di conversione implicita non devono generare eccezioni né determinare perdite di dati.</span><span class="sxs-lookup"><span data-stu-id="ffe2c-108">In general, implicit conversion operators should never throw exceptions and never lose information so that they can be used safely without the programmer's awareness.</span></span> <span data-ttu-id="ffe2c-109">Se un operatore di conversione non soddisfa questi requisiti, è opportuno contrassegnarlo come `explicit`.</span><span class="sxs-lookup"><span data-stu-id="ffe2c-109">If a conversion operator cannot meet those criteria, it should be marked `explicit`.</span></span> <span data-ttu-id="ffe2c-110">Per altre informazioni, vedere [Uso degli operatori di conversione](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="ffe2c-110">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ffe2c-111">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="ffe2c-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ffe2c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffe2c-112">See Also</span></span>  
 [<span data-ttu-id="ffe2c-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="ffe2c-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ffe2c-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ffe2c-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ffe2c-115">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="ffe2c-115">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ffe2c-116">explicit</span><span class="sxs-lookup"><span data-stu-id="ffe2c-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
 [<span data-ttu-id="ffe2c-117">operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="ffe2c-117">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 [<span data-ttu-id="ffe2c-118">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="ffe2c-118">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
