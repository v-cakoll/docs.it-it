---
title: Vincolo new (Riferimenti per C#)
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 9948fc65030a4636c5d23db4ef8c3a584018d2f5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482151"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="1bbfa-102">Vincolo new (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1bbfa-102">new constraint (C# Reference)</span></span>

<span data-ttu-id="1bbfa-103">Il vincolo `new` specifica che qualsiasi argomento di tipo in una dichiarazione di classe generica deve avere un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="1bbfa-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="1bbfa-104">Per usare il vincolo new, il tipo non può essere astratto.</span><span class="sxs-lookup"><span data-stu-id="1bbfa-104">To use the new constraint, the type cannot be abstract.</span></span>

## <a name="example"></a><span data-ttu-id="1bbfa-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bbfa-105">Example</span></span>

<span data-ttu-id="1bbfa-106">Applicare il vincolo `new` a un parametro del tipo quando la classe generica crea nuove istanze del tipo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1bbfa-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

## <a name="example"></a><span data-ttu-id="1bbfa-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bbfa-107">Example</span></span>

<span data-ttu-id="1bbfa-108">Quando il vincolo `new()` viene usato con altri vincoli, è necessario specificarlo per ultimo:</span><span class="sxs-lookup"><span data-stu-id="1bbfa-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="1bbfa-109">Per altre informazioni, vedere [Vincoli sui parametri di tipo](../../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="1bbfa-109">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1bbfa-110">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="1bbfa-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1bbfa-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bbfa-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="1bbfa-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="1bbfa-112">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="1bbfa-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1bbfa-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1bbfa-114">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="1bbfa-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1bbfa-115">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="1bbfa-115">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="1bbfa-116">Generics</span><span class="sxs-lookup"><span data-stu-id="1bbfa-116">Generics</span></span>](../../programming-guide/generics/index.md)