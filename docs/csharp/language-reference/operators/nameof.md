---
title: espressione NameOf-riferimenti per C#
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: d71acf0cf7d5cdcfa5310455af2120fa1f82d567
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135919"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="8a0b9-102">espressione NameOf (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="8a0b9-102">nameof expression (C# reference)</span></span>

<span data-ttu-id="8a0b9-103">Un' `nameof` espressione produce il nome di una variabile, di un tipo o di un membro come costante stringa:</span><span class="sxs-lookup"><span data-stu-id="8a0b9-103">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

<span data-ttu-id="8a0b9-104">Come illustrato nell'esempio precedente, nel caso di un tipo e di uno spazio dei nomi, il nome prodotto in genere non è [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="8a0b9-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="8a0b9-105">Nel caso degli [identificatori Verbatim](../tokens/verbatim.md), il `@` carattere non è la parte di un nome, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8a0b9-105">In the case of [verbatim identifiers](../tokens/verbatim.md), the `@` character is not the part of a name, as the following example shows:</span></span>

[!code-csharp-interactive[nameof verbatim](snippets/NameOfOperator.cs#Verbatim)]

<span data-ttu-id="8a0b9-106">Un' `nameof` espressione viene valutata in fase di compilazione e non ha alcun effetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8a0b9-106">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="8a0b9-107">È possibile usare un' `nameof` espressione per rendere più gestibile il codice per il controllo degli argomenti:</span><span class="sxs-lookup"><span data-stu-id="8a0b9-107">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="8a0b9-108">Un' `nameof` espressione è disponibile in C# 6 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="8a0b9-108">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8a0b9-109">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="8a0b9-109">C# language specification</span></span>

<span data-ttu-id="8a0b9-110">Per altre informazioni, vedere la sezione [Espressioni Nameof](~/_csharplang/spec/expressions.md#nameof-expressions) in [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="8a0b9-110">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8a0b9-111">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="8a0b9-111">See also</span></span>

- [<span data-ttu-id="8a0b9-112">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="8a0b9-112">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8a0b9-113">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="8a0b9-113">C# operators</span></span>](index.md)
