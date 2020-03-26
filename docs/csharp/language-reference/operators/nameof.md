---
title: nomedellespressione - Informazioni di riferimento su C
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 5a68161be7bb03122d2a63ccef4365c5853862b2
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507139"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="0b12f-102">nomedell espressione (riferimenti per C</span><span class="sxs-lookup"><span data-stu-id="0b12f-102">nameof expression (C# reference)</span></span>

<span data-ttu-id="0b12f-103">Un'espressione produce il nome di una variabile, un tipo o un membro come costante di stringa:A `nameof` expression produces the name of a variable, type, or member as the string constant:</span><span class="sxs-lookup"><span data-stu-id="0b12f-103">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

<span data-ttu-id="0b12f-104">Come illustrato nell'esempio precedente, nel caso di un tipo e di uno spazio dei nomi, il nome prodotto in genere non è [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="0b12f-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="0b12f-105">Un'espressione `nameof` viene valutata in fase di compilazione e non ha alcun effetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0b12f-105">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="0b12f-106">È possibile `nameof` utilizzare un'espressione per rendere più gestibile il codice di controllo degli argomenti:You can use a expression to make the argument-checking code more maintainable:</span><span class="sxs-lookup"><span data-stu-id="0b12f-106">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="0b12f-107">Un'espressione `nameof` è disponibile in C , 6 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="0b12f-107">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0b12f-108">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0b12f-108">C# language specification</span></span>

<span data-ttu-id="0b12f-109">Per altre informazioni, vedere la sezione [Espressioni Nameof](~/_csharplang/spec/expressions.md#nameof-expressions) in [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="0b12f-109">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0b12f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b12f-110">See also</span></span>

- [<span data-ttu-id="0b12f-111">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="0b12f-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0b12f-112">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="0b12f-112">C# operators</span></span>](index.md)
