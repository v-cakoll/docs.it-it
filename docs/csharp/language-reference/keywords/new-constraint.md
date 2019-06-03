---
title: Vincolo new - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 2aa68bec13322e332bfe3841bc99403f72301183
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421794"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="32e70-102">Vincolo new (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="32e70-102">new constraint (C# Reference)</span></span>

<span data-ttu-id="32e70-103">Il vincolo `new` specifica che qualsiasi argomento di tipo in una dichiarazione di classe generica deve avere un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="32e70-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="32e70-104">Per usare il vincolo new, il tipo non può essere astratto.</span><span class="sxs-lookup"><span data-stu-id="32e70-104">To use the new constraint, the type cannot be abstract.</span></span>

## <a name="example"></a><span data-ttu-id="32e70-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="32e70-105">Example</span></span>

<span data-ttu-id="32e70-106">Applicare il vincolo `new` a un parametro del tipo quando la classe generica crea nuove istanze del tipo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="32e70-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

## <a name="example"></a><span data-ttu-id="32e70-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="32e70-107">Example</span></span>

<span data-ttu-id="32e70-108">Quando il vincolo `new()` viene usato con altri vincoli, è necessario specificarlo per ultimo:</span><span class="sxs-lookup"><span data-stu-id="32e70-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="32e70-109">Per altre informazioni, vedere [Vincoli sui parametri di tipo](../../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="32e70-109">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="32e70-110">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="32e70-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="32e70-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32e70-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="32e70-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="32e70-112">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="32e70-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="32e70-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="32e70-114">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="32e70-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="32e70-115">Generics</span><span class="sxs-lookup"><span data-stu-id="32e70-115">Generics</span></span>](../../programming-guide/generics/index.md)
