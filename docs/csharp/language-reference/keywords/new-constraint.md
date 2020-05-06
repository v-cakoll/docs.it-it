---
title: Vincolo new - Riferimenti per C#
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 6f6d1b663d03dc9b3adf0e7055dcffacc79d83dc
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795339"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="6dbd7-102">Vincolo new (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="6dbd7-102">new constraint (C# Reference)</span></span>

<span data-ttu-id="6dbd7-103">Il vincolo `new` specifica che un argomento tipo in una dichiarazione di classe generica deve avere un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="6dbd7-103">The `new` constraint specifies that a type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="6dbd7-104">Per usare il vincolo `new`, il tipo non può essere astratto.</span><span class="sxs-lookup"><span data-stu-id="6dbd7-104">To use the `new` constraint, the type cannot be abstract.</span></span>

<span data-ttu-id="6dbd7-105">Applicare il vincolo `new` a un parametro di tipo quando una classe generica crea nuove istanze del tipo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="6dbd7-105">Apply the `new` constraint to a type parameter when a generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

<span data-ttu-id="6dbd7-106">Quando il vincolo `new()` viene usato con altri vincoli, è necessario specificarlo per ultimo:</span><span class="sxs-lookup"><span data-stu-id="6dbd7-106">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="6dbd7-107">Per altre informazioni, vedere [Vincoli sui parametri di tipo](../../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="6dbd7-107">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="6dbd7-108">È anche possibile usare la parola chiave `new` per [creare un'istanza di un tipo](../operators/new-operator.md) o come [modificatore di dichiarazione di membro](new-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="6dbd7-108">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [member declaration modifier](new-modifier.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6dbd7-109">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="6dbd7-109">C# language specification</span></span>

<span data-ttu-id="6dbd7-110">Per altre informazioni, vedere la sezione [Vincoli del parametro di tipo](~/_csharplang/spec/classes.md#type-parameter-constraints) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="6dbd7-110">For more information, see the [Type parameter constraints](~/_csharplang/spec/classes.md#type-parameter-constraints) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6dbd7-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6dbd7-111">See also</span></span>

- [<span data-ttu-id="6dbd7-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="6dbd7-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6dbd7-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="6dbd7-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6dbd7-114">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="6dbd7-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="6dbd7-115">Generics</span><span class="sxs-lookup"><span data-stu-id="6dbd7-115">Generics</span></span>](../../programming-guide/generics/index.md)
