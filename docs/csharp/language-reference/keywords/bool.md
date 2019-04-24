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
ms.openlocfilehash: d87da29872582e9c0d47a6c999312ce88252a5cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334172"
---
# <a name="bool-c-reference"></a><span data-ttu-id="0e3e7-102">bool (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0e3e7-102">bool (C# Reference)</span></span>

<span data-ttu-id="0e3e7-103">La parola chiave `bool` è un alias per <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0e3e7-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0e3e7-104">Viene usata per dichiarare le variabili che archiviano i valori booleani, [true](true-literal.md) e [false](false-literal.md).</span><span class="sxs-lookup"><span data-stu-id="0e3e7-104">It is used to declare variables to store the Boolean values: [true](true-literal.md) and [false](false-literal.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0e3e7-105">Usare il tipo `bool?` se occorre supportare la logica a tre valori, ad esempio quando si lavora con database che supportano un tipo booleano a tre valori.</span><span class="sxs-lookup"><span data-stu-id="0e3e7-105">Use the `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="0e3e7-106">Per gli operandi `bool?`, gli operatori `&` e `|` predefiniti supportano la logica a tre valori.</span><span class="sxs-lookup"><span data-stu-id="0e3e7-106">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="0e3e7-107">Per altre informazioni, vedere la sezione [Operatori logici booleani nullable](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) dell'articolo [Operatori logici booleani](../operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="0e3e7-107">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

## <a name="literals"></a><span data-ttu-id="0e3e7-108">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="0e3e7-108">Literals</span></span>

<span data-ttu-id="0e3e7-109">È possibile assegnare un valore booleano a una variabile `bool`.</span><span class="sxs-lookup"><span data-stu-id="0e3e7-109">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="0e3e7-110">È possibile anche assegnare un'espressione che restituisce `bool` per una variabile `bool`.</span><span class="sxs-lookup"><span data-stu-id="0e3e7-110">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="0e3e7-111">Il valore predefinito di una variabile `bool` è `false`.</span><span class="sxs-lookup"><span data-stu-id="0e3e7-111">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="0e3e7-112">Il valore predefinito di una variabile `bool?` è `null`.</span><span class="sxs-lookup"><span data-stu-id="0e3e7-112">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="0e3e7-113">Conversioni</span><span class="sxs-lookup"><span data-stu-id="0e3e7-113">Conversions</span></span>

<span data-ttu-id="0e3e7-114">In C++, un valore di tipo `bool` può essere convertito in un valore di tipo `int`; in altre parole, `false` equivale a zero e `true` equivale a valori diversi da zero.</span><span class="sxs-lookup"><span data-stu-id="0e3e7-114">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="0e3e7-115">In C#, non c'è nessuna conversione tra il tipo `bool` e altri tipi.</span><span class="sxs-lookup"><span data-stu-id="0e3e7-115">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="0e3e7-116">Ad esempio, l'istruzione `if` seguente non è valida in C#:</span><span class="sxs-lookup"><span data-stu-id="0e3e7-116">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="0e3e7-117">Per testare una variabile del tipo `int`, è necessario confrontarla esplicitamente con un valore, ad esempio zero, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0e3e7-117">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="0e3e7-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e3e7-118">Example</span></span>

<span data-ttu-id="0e3e7-119">In questo esempio si immette un carattere dalla tastiera e il programma controlla se il carattere di input è una lettera.</span><span class="sxs-lookup"><span data-stu-id="0e3e7-119">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="0e3e7-120">Se è una lettera, controlla se è maiuscola o minuscola.</span><span class="sxs-lookup"><span data-stu-id="0e3e7-120">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="0e3e7-121">Questi controlli vengono eseguiti con <xref:System.Char.IsLetter%2A> e <xref:System.Char.IsLower%2A>, che restituiscono entrambi il tipo `bool`:</span><span class="sxs-lookup"><span data-stu-id="0e3e7-121">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="0e3e7-122">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0e3e7-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0e3e7-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e3e7-123">See also</span></span>

- [<span data-ttu-id="0e3e7-124">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="0e3e7-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="0e3e7-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0e3e7-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="0e3e7-126">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="0e3e7-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="0e3e7-127">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="0e3e7-127">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)
- [<span data-ttu-id="0e3e7-128">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="0e3e7-128">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="0e3e7-129">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="0e3e7-129">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="0e3e7-130">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="0e3e7-130">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
