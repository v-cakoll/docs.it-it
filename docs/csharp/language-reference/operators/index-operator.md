---
title: Operatore [] - Riferimenti per C#
ms.custom: seodec18
ms.date: 01/10/2019
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 948ce238058307631cf0e5a7a5e3d72664233052
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333395"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="51d8a-102">Operatore [] (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="51d8a-102">[] operator (C# Reference)</span></span>

<span data-ttu-id="51d8a-103">Le parentesi quadre `[]` vengono in genere usate per l'accesso agli elementi matrice, indicizzatore o puntatore.</span><span class="sxs-lookup"><span data-stu-id="51d8a-103">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

<span data-ttu-id="51d8a-104">Per altre informazioni sull'accesso all'elemento puntatore, vedere [Procedura: Accedere a un elemento di matrice con un puntatore](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="51d8a-104">For more information about pointer element access, see [How to: access an array element with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).</span></span>

<span data-ttu-id="51d8a-105">Le parentesi quadre possono anche essere usate per specificare [attributi](../../programming-guide/concepts/attributes/index.md):</span><span class="sxs-lookup"><span data-stu-id="51d8a-105">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="array-access"></a><span data-ttu-id="51d8a-106">Accesso a matrici</span><span class="sxs-lookup"><span data-stu-id="51d8a-106">Array access</span></span>

<span data-ttu-id="51d8a-107">Nell'esempio seguente viene illustrato come accedere agli elementi matrice:</span><span class="sxs-lookup"><span data-stu-id="51d8a-107">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Arrays)]

<span data-ttu-id="51d8a-108">Se un indice di matrice è fuori dai limiti della dimensione corrispondente di una matrice, viene generata un'eccezione <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="51d8a-108">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="51d8a-109">Come illustrato nell'esempio precedente, le parentesi quadre vengono usate anche nella dichiarazione di un tipo matrice e nella creazione di istanze di matrice.</span><span class="sxs-lookup"><span data-stu-id="51d8a-109">As the preceding example shows, you also use square brackets in declaration of an array type and instantiation of array instances.</span></span>

<span data-ttu-id="51d8a-110">Per altre informazioni sulle matrici, vedere [Matrici](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="51d8a-110">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="indexer-access"></a><span data-ttu-id="51d8a-111">Accesso all'indicizzatore</span><span class="sxs-lookup"><span data-stu-id="51d8a-111">Indexer access</span></span>

<span data-ttu-id="51d8a-112">Nell'esempio seguente viene usato il tipo .NET <xref:System.Collections.Generic.Dictionary%602> per dimostrare l'accesso all'indicizzatore:</span><span class="sxs-lookup"><span data-stu-id="51d8a-112">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Indexers)]

<span data-ttu-id="51d8a-113">Gli indicizzatori consentono di indicizzare le istanze di un tipo definito dall'utente con modalità simili a quelle dell'indicizzazione della matrice.</span><span class="sxs-lookup"><span data-stu-id="51d8a-113">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="51d8a-114">A differenza degli indici di matrice, che devono essere valori interi, gli argomenti dell'indicizzatore possono essere dichiarati con qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="51d8a-114">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="51d8a-115">Per altre informazioni sugli indicizzatori, vedere [Indicizzatori](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="51d8a-115">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="51d8a-116">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="51d8a-116">Operator overloadability</span></span>

<span data-ttu-id="51d8a-117">L'accesso all'elemento `[]` non viene considerato come operatore con supporto dell'overload.</span><span class="sxs-lookup"><span data-stu-id="51d8a-117">Element access `[]` is not considered an overloadable operator.</span></span> <span data-ttu-id="51d8a-118">Per il supporto dell'indicizzazione con tipi definiti dall'utente, usare gli [indicizzatori](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="51d8a-118">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="51d8a-119">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="51d8a-119">C# language specification</span></span>

<span data-ttu-id="51d8a-120">Per altre informazioni, vedere le sezioni [Accesso all'elemento](~/_csharplang/spec/expressions.md#element-access) e [Accesso ai membri del puntatore](~/_csharplang/spec/unsafe-code.md#pointer-element-access) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="51d8a-120">For more information, see the [Element access](~/_csharplang/spec/expressions.md#element-access) and [Pointer element access](~/_csharplang/spec/unsafe-code.md#pointer-element-access) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="51d8a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51d8a-121">See also</span></span>

- [<span data-ttu-id="51d8a-122">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="51d8a-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="51d8a-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="51d8a-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="51d8a-124">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="51d8a-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="51d8a-125">Matrici</span><span class="sxs-lookup"><span data-stu-id="51d8a-125">Arrays</span></span>](../../programming-guide/arrays/index.md)
- [<span data-ttu-id="51d8a-126">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="51d8a-126">Indexers</span></span>](../../programming-guide/indexers/index.md)
- [<span data-ttu-id="51d8a-127">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="51d8a-127">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="51d8a-128">Attributi</span><span class="sxs-lookup"><span data-stu-id="51d8a-128">Attributes</span></span>](../../programming-guide/concepts/attributes/index.md)