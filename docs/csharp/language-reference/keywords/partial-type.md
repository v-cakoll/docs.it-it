---
title: partial (Tipo) (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 365d00d2c53d3efe1cd4330bdd3ec48740a49c53
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43422329"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="3b6c0-102">partial (Tipo) (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3b6c0-102">partial type (C# Reference)</span></span>

<span data-ttu-id="3b6c0-103">Le definizioni di tipi parziali consentono la suddivisione in più file della definizione di una classe, una struttura o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3b6c0-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>

<span data-ttu-id="3b6c0-104">In *File1.cs*:</span><span class="sxs-lookup"><span data-stu-id="3b6c0-104">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="3b6c0-105">In *File2.cs* la dichiarazione:</span><span class="sxs-lookup"><span data-stu-id="3b6c0-105">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="3b6c0-106">Note</span><span class="sxs-lookup"><span data-stu-id="3b6c0-106">Remarks</span></span>

<span data-ttu-id="3b6c0-107">La suddivisione di un tipo di classe, struttura o interfaccia in più file può essere utile per progetti di grandi dimensioni o quando si usa codice generato automaticamente come quello fornito da [Progettazione Windows Form](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="3b6c0-107">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="3b6c0-108">Un tipo parziale può contenere un [metodo parziale](partial-method.md).</span><span class="sxs-lookup"><span data-stu-id="3b6c0-108">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="3b6c0-109">Per altre informazioni, vedere [Classi e metodi parziali](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="3b6c0-109">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3b6c0-110">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="3b6c0-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="3b6c0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b6c0-111">See also</span></span>

- [<span data-ttu-id="3b6c0-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="3b6c0-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3b6c0-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3b6c0-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3b6c0-114">Modificatori</span><span class="sxs-lookup"><span data-stu-id="3b6c0-114">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="3b6c0-115">Introduzione ai generics</span><span class="sxs-lookup"><span data-stu-id="3b6c0-115">Introduction to Generics</span></span>](../../programming-guide/generics/introduction-to-generics.md)