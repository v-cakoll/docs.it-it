---
title: typeof - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: f218414bf60a86b95461d747fb6c557f03bcfcb3
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2019
ms.locfileid: "57846116"
---
# <a name="typeof-c-reference"></a><span data-ttu-id="512b3-102">typeof (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="512b3-102">typeof (C# Reference)</span></span>

<span data-ttu-id="512b3-103">Viene usato per ottenere l'oggetto <xref:System.Type?displayProperty=nameWithType> per un tipo.</span><span class="sxs-lookup"><span data-stu-id="512b3-103">Used to obtain the <xref:System.Type?displayProperty=nameWithType> object for a type.</span></span> <span data-ttu-id="512b3-104">L'espressione `typeof` assume il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="512b3-104">A `typeof` expression takes the following form:</span></span>

```csharp
System.Type type = typeof(int);
```

## <a name="remarks"></a><span data-ttu-id="512b3-105">Note</span><span class="sxs-lookup"><span data-stu-id="512b3-105">Remarks</span></span>

<span data-ttu-id="512b3-106">Per ottenere il tipo di runtime di un'espressione, è possibile usare il metodo di .NET Framework <xref:System.Object.GetType%2A>, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="512b3-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>

```csharp
int i = 0;
System.Type type = i.GetType();
```

<span data-ttu-id="512b3-107">Non è possibile sottoporre l'operatore `typeof` a overload.</span><span class="sxs-lookup"><span data-stu-id="512b3-107">The `typeof` operator cannot be overloaded.</span></span>

<span data-ttu-id="512b3-108">L'operatore `typeof` può essere usato anche su tipi generici aperti.</span><span class="sxs-lookup"><span data-stu-id="512b3-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="512b3-109">I tipi con più di un parametro di tipo devono avere il numero appropriato di virgole nella specifica.</span><span class="sxs-lookup"><span data-stu-id="512b3-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="512b3-110"><xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWIthType>, ad esempio, ha due argomenti tipo, quindi si usa una virgola:</span><span class="sxs-lookup"><span data-stu-id="512b3-110">For example, the <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWIthType> has two type arguments, so you use one comma:</span></span>

```csharp
Type t = typeof(System.Collection.Generic.Dictionary<,>);
```

<span data-ttu-id="512b3-111">Nell'esempio seguente viene illustrato come determinare se il tipo restituito di un metodo è un elemento <xref:System.Collections.Generic.IEnumerable%601> generico.</span><span class="sxs-lookup"><span data-stu-id="512b3-111">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="512b3-112"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> restituirà `null` se il tipo restituito non è un tipo generico <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="512b3-112"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> will return `null` if the return type is not an <xref:System.Collections.Generic.IEnumerable%601> generic type.</span></span>

[!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]

## <a name="example"></a><span data-ttu-id="512b3-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="512b3-113">Example</span></span>

[!code-csharp[csrefKeywordsOperator#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#12)] 

## <a name="example"></a><span data-ttu-id="512b3-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="512b3-114">Example</span></span>

<span data-ttu-id="512b3-115">Questo esempio usa il metodo <xref:System.Object.GetType%2A> per determinare il tipo usato per contenere il risultato di un calcolo numerico.</span><span class="sxs-lookup"><span data-stu-id="512b3-115">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="512b3-116">Ciò dipende dai requisiti di archiviazione del numero risultante.</span><span class="sxs-lookup"><span data-stu-id="512b3-116">This depends on the storage requirements of the resulting number.</span></span>

[!code-csharp[csrefKeywordsOperator#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#13)]

## <a name="c-language-specification"></a><span data-ttu-id="512b3-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="512b3-117">C# language specification</span></span>

<span data-ttu-id="512b3-118">Per altre informazioni, vedere [Operatore typeof](~/_csharplang/spec/expressions.md#the-typeof-operator) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="512b3-118">For more information, see [The typeof operator](~/_csharplang/spec/expressions.md#the-typeof-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="512b3-119">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="512b3-119">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="512b3-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="512b3-120">See also</span></span>

- <xref:System.Type?displayProperty=nameWithType>
- [<span data-ttu-id="512b3-121">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="512b3-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="512b3-122">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="512b3-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="512b3-123">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="512b3-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="512b3-124">is</span><span class="sxs-lookup"><span data-stu-id="512b3-124">is</span></span>](../../../csharp/language-reference/keywords/is.md)
- [<span data-ttu-id="512b3-125">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="512b3-125">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
