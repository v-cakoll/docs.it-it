---
title: implicit (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- implicit
- implicit_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
caps.latest.revision: 19
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
ms.openlocfilehash: e4452a3bb6da2d0d294ca26d6b957f2c1c4402fd
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="implicit-c-reference"></a><span data-ttu-id="fdf45-102">implicit (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="fdf45-102">implicit (C# Reference)</span></span>
<span data-ttu-id="fdf45-103">La parola chiave `implicit` viene usata per dichiarare un operatore di conversione implicita di tipi definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="fdf45-103">The `implicit` keyword is used to declare an implicit user-defined type conversion operator.</span></span> <span data-ttu-id="fdf45-104">È possibile usare questa parola chiave per abilitare le conversioni implicite tra un tipo definito dall'utente e un altro tipo, se è garantito che tale conversione non provoca una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="fdf45-104">Use it to enable implicit conversions between a user-defined type and another type, if the conversion is guaranteed not to cause a loss of data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdf45-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="fdf45-105">Example</span></span>  
 <span data-ttu-id="fdf45-106">[!code-cs[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fdf45-106">[!code-cs[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]</span></span>  
  
 <span data-ttu-id="fdf45-107">Grazie all'eliminazione dei cast non necessari, le conversioni implicite contribuiscono a migliorare la leggibilità del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="fdf45-107">By eliminating unnecessary casts, implicit conversions can improve source code readability.</span></span> <span data-ttu-id="fdf45-108">Tuttavia, poiché per le conversioni implicite non è necessario eseguire il cast in modo esplicito da un tipo all'altro, è importante assicurarsi di non ottenere risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="fdf45-108">However, because implicit conversions do not require programmers to explicitly cast from one type to the other, care must be taken to prevent unexpected results.</span></span> <span data-ttu-id="fdf45-109">In genere, per poter essere usati in modo sicuro senza il controllo del programmatore, gli operatori di conversione implicita non devono generare eccezioni né determinare perdite di dati.</span><span class="sxs-lookup"><span data-stu-id="fdf45-109">In general, implicit conversion operators should never throw exceptions and never lose information so that they can be used safely without the programmer's awareness.</span></span> <span data-ttu-id="fdf45-110">Se un operatore di conversione non soddisfa questi requisiti, è opportuno contrassegnarlo come `explicit`.</span><span class="sxs-lookup"><span data-stu-id="fdf45-110">If a conversion operator cannot meet those criteria, it should be marked `explicit`.</span></span> <span data-ttu-id="fdf45-111">Per altre informazioni, vedere [Uso degli operatori di conversione](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="fdf45-111">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="fdf45-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="fdf45-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fdf45-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdf45-113">See Also</span></span>  
 <span data-ttu-id="fdf45-114">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="fdf45-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="fdf45-115">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fdf45-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fdf45-116">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="fdf45-116">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="fdf45-117">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span><span class="sxs-lookup"><span data-stu-id="fdf45-117">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span></span>  
 <span data-ttu-id="fdf45-118">[operator (Riferimenti per C#)](../../../csharp/language-reference/keywords/operator.md) </span><span class="sxs-lookup"><span data-stu-id="fdf45-118">[operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md) </span></span>  
 [<span data-ttu-id="fdf45-119">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="fdf45-119">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

