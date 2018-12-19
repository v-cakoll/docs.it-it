---
title: object - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
ms.openlocfilehash: a1917a7925d4ed90ede40248fa394f9c45d09b4e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238969"
---
# <a name="object-c-reference"></a><span data-ttu-id="b7f3b-102">object (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b7f3b-102">object (C# Reference)</span></span>

<span data-ttu-id="b7f3b-103">Il tipo `object` è un alias per <xref:System.Object> in .NET.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-103">The `object` type is an alias for <xref:System.Object> in .NET.</span></span> <span data-ttu-id="b7f3b-104">Nel sistema di tipi unificato di C#, tutti i tipi, predefiniti e definiti dall'utente, i tipi riferimento e i tipi valore ereditano direttamente o indirettamente da <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-104">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span> <span data-ttu-id="b7f3b-105">Alle variabili di tipo `object` è possibile assegnare valori di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-105">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="b7f3b-106">Una variabile di un tipo di valore convertita in oggetto viene definita *boxed*.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-106">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="b7f3b-107">Una variabile di tipo object convertita in un tipo di valore viene definita *unboxed*.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-107">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="b7f3b-108">Per altre informazioni, vedere [Boxing e unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="b7f3b-108">For more information, see [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>

## <a name="example"></a><span data-ttu-id="b7f3b-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7f3b-109">Example</span></span>

<span data-ttu-id="b7f3b-110">L'esempio seguente descrive come le variabili di tipo `object` possono accettare valori di qualsiasi tipo di dati e come le variabili di tipo `object` possono usare i metodi in <xref:System.Object> da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-110">The following sample shows how variables of type `object` can accept values of any data type and how variables of type `object` can use methods on <xref:System.Object> from the .NET Framework.</span></span>

[!code-csharp[csrefKeywordsTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#16)]

## <a name="c-language-specification"></a><span data-ttu-id="b7f3b-111">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b7f3b-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b7f3b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7f3b-112">See also</span></span>

- [<span data-ttu-id="b7f3b-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b7f3b-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b7f3b-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b7f3b-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b7f3b-115">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="b7f3b-115">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b7f3b-116">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="b7f3b-116">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="b7f3b-117">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="b7f3b-117">Value Types</span></span>](value-types.md)