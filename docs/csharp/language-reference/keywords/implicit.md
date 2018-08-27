---
title: implicit (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
ms.openlocfilehash: 70379136fd4b14403eac919ac15590250b17b416
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932731"
---
# <a name="implicit-c-reference"></a><span data-ttu-id="fc9a0-102">implicit (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="fc9a0-102">implicit (C# Reference)</span></span>

<span data-ttu-id="fc9a0-103">La parola chiave `implicit` viene usata per dichiarare un operatore di conversione implicita di tipi definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="fc9a0-103">The `implicit` keyword is used to declare an implicit user-defined type conversion operator.</span></span> <span data-ttu-id="fc9a0-104">È possibile usare questa parola chiave per abilitare le conversioni implicite tra un tipo definito dall'utente e un altro tipo, se è garantito che tale conversione non provoca una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="fc9a0-104">Use it to enable implicit conversions between a user-defined type and another type, if the conversion is guaranteed not to cause a loss of data.</span></span>

## <a name="example"></a><span data-ttu-id="fc9a0-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc9a0-105">Example</span></span>

[!code-csharp[csrefKeywordsConversion#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#5)]

<span data-ttu-id="fc9a0-106">Grazie all'eliminazione dei cast non necessari, le conversioni implicite contribuiscono a migliorare la leggibilità del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="fc9a0-106">By eliminating unnecessary casts, implicit conversions can improve source code readability.</span></span> <span data-ttu-id="fc9a0-107">Tuttavia, poiché per le conversioni implicite non è necessario eseguire il cast in modo esplicito da un tipo all'altro, è importante assicurarsi di non ottenere risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="fc9a0-107">However, because implicit conversions do not require programmers to explicitly cast from one type to the other, care must be taken to prevent unexpected results.</span></span> <span data-ttu-id="fc9a0-108">In genere, per poter essere usati in modo sicuro senza il controllo del programmatore, gli operatori di conversione implicita non devono generare eccezioni né determinare perdite di dati.</span><span class="sxs-lookup"><span data-stu-id="fc9a0-108">In general, implicit conversion operators should never throw exceptions and never lose information so that they can be used safely without the programmer's awareness.</span></span> <span data-ttu-id="fc9a0-109">Se un operatore di conversione non soddisfa questi requisiti, è opportuno contrassegnarlo come `explicit`.</span><span class="sxs-lookup"><span data-stu-id="fc9a0-109">If a conversion operator cannot meet those criteria, it should be marked `explicit`.</span></span> <span data-ttu-id="fc9a0-110">Per altre informazioni, vedere [Uso degli operatori di conversione](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="fc9a0-110">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fc9a0-111">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="fc9a0-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="fc9a0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc9a0-112">See also</span></span>

- [<span data-ttu-id="fc9a0-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="fc9a0-113">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="fc9a0-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="fc9a0-114">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="fc9a0-115">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="fc9a0-115">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="fc9a0-116">explicit</span><span class="sxs-lookup"><span data-stu-id="fc9a0-116">explicit</span></span>](explicit.md)  
- [<span data-ttu-id="fc9a0-117">operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="fc9a0-117">operator (C# Reference)</span></span>](operator.md)  
- [<span data-ttu-id="fc9a0-118">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="fc9a0-118">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
