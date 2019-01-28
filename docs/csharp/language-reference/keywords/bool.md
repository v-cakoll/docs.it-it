---
title: Parola chiave bool - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 958b58b31193dbf4c03709e4ab7ba38f7f30e0ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590481"
---
# <a name="bool-c-reference"></a><span data-ttu-id="7edc4-102">bool (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7edc4-102">bool (C# Reference)</span></span>

<span data-ttu-id="7edc4-103">La parola chiave `bool` è un alias per <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7edc4-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7edc4-104">Viene usata per dichiarare le variabili che archiviano i valori booleani, [true](true-literal.md) e [false](false-literal.md).</span><span class="sxs-lookup"><span data-stu-id="7edc4-104">It is used to declare variables to store the Boolean values: [true](true-literal.md) and [false](false-literal.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7edc4-105">Se è necessaria una variabile booleana che può anche avere un valore di `null`, usare `bool?`.</span><span class="sxs-lookup"><span data-stu-id="7edc4-105">If you require a Boolean variable that can also have a value of `null`, use `bool?`.</span></span> <span data-ttu-id="7edc4-106">Per altre informazioni, vedere la sezione [Tipo bool?](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) dell'articolo [Uso dei tipi nullable](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="7edc4-106">For more information, see [The bool? type](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

## <a name="literals"></a><span data-ttu-id="7edc4-107">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="7edc4-107">Literals</span></span>

<span data-ttu-id="7edc4-108">È possibile assegnare un valore booleano a una variabile `bool`.</span><span class="sxs-lookup"><span data-stu-id="7edc4-108">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="7edc4-109">È possibile anche assegnare un'espressione che restituisce `bool` per una variabile `bool`.</span><span class="sxs-lookup"><span data-stu-id="7edc4-109">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="7edc4-110">Il valore predefinito di una variabile `bool` è `false`.</span><span class="sxs-lookup"><span data-stu-id="7edc4-110">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="7edc4-111">Il valore predefinito di una variabile `bool?` è `null`.</span><span class="sxs-lookup"><span data-stu-id="7edc4-111">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="7edc4-112">Conversioni</span><span class="sxs-lookup"><span data-stu-id="7edc4-112">Conversions</span></span>

<span data-ttu-id="7edc4-113">In C++, un valore di tipo `bool` può essere convertito in un valore di tipo `int`; in altre parole, `false` equivale a zero e `true` equivale a valori diversi da zero.</span><span class="sxs-lookup"><span data-stu-id="7edc4-113">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="7edc4-114">In C#, non c'è nessuna conversione tra il tipo `bool` e altri tipi.</span><span class="sxs-lookup"><span data-stu-id="7edc4-114">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="7edc4-115">Ad esempio, l'istruzione `if` seguente non è valida in C#:</span><span class="sxs-lookup"><span data-stu-id="7edc4-115">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="7edc4-116">Per testare una variabile del tipo `int`, è necessario confrontarla esplicitamente con un valore, ad esempio zero, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7edc4-116">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="7edc4-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="7edc4-117">Example</span></span>

<span data-ttu-id="7edc4-118">In questo esempio si immette un carattere dalla tastiera e il programma controlla se il carattere di input è una lettera.</span><span class="sxs-lookup"><span data-stu-id="7edc4-118">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="7edc4-119">Se è una lettera, controlla se è maiuscola o minuscola.</span><span class="sxs-lookup"><span data-stu-id="7edc4-119">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="7edc4-120">Questi controlli vengono eseguiti con <xref:System.Char.IsLetter%2A> e <xref:System.Char.IsLower%2A>, che restituiscono entrambi il tipo `bool`:</span><span class="sxs-lookup"><span data-stu-id="7edc4-120">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="7edc4-121">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7edc4-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7edc4-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7edc4-122">See also</span></span>

- [<span data-ttu-id="7edc4-123">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="7edc4-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="7edc4-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7edc4-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="7edc4-125">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="7edc4-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="7edc4-126">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="7edc4-126">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)
- [<span data-ttu-id="7edc4-127">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="7edc4-127">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="7edc4-128">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="7edc4-128">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="7edc4-129">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="7edc4-129">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
