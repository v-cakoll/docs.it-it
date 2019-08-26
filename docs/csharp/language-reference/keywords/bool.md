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
ms.openlocfilehash: 3e4e83b52cd6b275e68039693c774f6490f2b88f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606054"
---
# <a name="bool-c-reference"></a><span data-ttu-id="1bc21-102">bool (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1bc21-102">bool (C# Reference)</span></span>

<span data-ttu-id="1bc21-103">La parola chiave `bool` è un alias per <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1bc21-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1bc21-104">Viene usata per dichiarare le variabili che archiviano i valori booleani, [true](true-literal.md) e [false](false-literal.md).</span><span class="sxs-lookup"><span data-stu-id="1bc21-104">It is used to declare variables to store the Boolean values: [true](true-literal.md) and [false](false-literal.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1bc21-105">Usare il tipo `bool?` se occorre supportare la logica a tre valori, ad esempio quando si lavora con database che supportano un tipo booleano a tre valori.</span><span class="sxs-lookup"><span data-stu-id="1bc21-105">Use the `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="1bc21-106">Per gli operandi `bool?`, gli operatori `&` e `|` predefiniti supportano la logica a tre valori.</span><span class="sxs-lookup"><span data-stu-id="1bc21-106">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="1bc21-107">Per altre informazioni, vedere la sezione [Operatori logici booleani nullable](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) dell'articolo [Operatori logici booleani](../operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="1bc21-107">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

## <a name="literals"></a><span data-ttu-id="1bc21-108">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="1bc21-108">Literals</span></span>

<span data-ttu-id="1bc21-109">È possibile assegnare un valore booleano a una variabile `bool`.</span><span class="sxs-lookup"><span data-stu-id="1bc21-109">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="1bc21-110">È possibile anche assegnare un'espressione che restituisce `bool` per una variabile `bool`.</span><span class="sxs-lookup"><span data-stu-id="1bc21-110">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="1bc21-111">Il valore predefinito di una variabile `bool` è `false`.</span><span class="sxs-lookup"><span data-stu-id="1bc21-111">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="1bc21-112">Il valore predefinito di una variabile `bool?` è `null`.</span><span class="sxs-lookup"><span data-stu-id="1bc21-112">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="1bc21-113">Conversioni</span><span class="sxs-lookup"><span data-stu-id="1bc21-113">Conversions</span></span>

<span data-ttu-id="1bc21-114">In C++, un valore di tipo `bool` può essere convertito in un valore di tipo `int`; in altre parole, `false` equivale a zero e `true` equivale a valori diversi da zero.</span><span class="sxs-lookup"><span data-stu-id="1bc21-114">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="1bc21-115">In C#, non c'è nessuna conversione tra il tipo `bool` e altri tipi.</span><span class="sxs-lookup"><span data-stu-id="1bc21-115">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="1bc21-116">Ad esempio, l'istruzione `if` seguente non è valida in C#:</span><span class="sxs-lookup"><span data-stu-id="1bc21-116">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="1bc21-117">Per testare una variabile del tipo `int`, è necessario confrontarla esplicitamente con un valore, ad esempio zero, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1bc21-117">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="1bc21-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bc21-118">Example</span></span>

<span data-ttu-id="1bc21-119">In questo esempio si immette un carattere dalla tastiera e il programma controlla se il carattere di input è una lettera.</span><span class="sxs-lookup"><span data-stu-id="1bc21-119">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="1bc21-120">Se è una lettera, controlla se è maiuscola o minuscola.</span><span class="sxs-lookup"><span data-stu-id="1bc21-120">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="1bc21-121">Questi controlli vengono eseguiti con <xref:System.Char.IsLetter%2A> e <xref:System.Char.IsLower%2A>, che restituiscono entrambi il tipo `bool`:</span><span class="sxs-lookup"><span data-stu-id="1bc21-121">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="1bc21-122">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="1bc21-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1bc21-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bc21-123">See also</span></span>

- [<span data-ttu-id="1bc21-124">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="1bc21-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1bc21-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1bc21-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1bc21-126">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="1bc21-126">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="1bc21-127">Tipi integrali</span><span class="sxs-lookup"><span data-stu-id="1bc21-127">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="1bc21-128">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="1bc21-128">Built-In Types Table</span></span>](./built-in-types-table.md)
- [<span data-ttu-id="1bc21-129">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="1bc21-129">Implicit Numeric Conversions Table</span></span>](./implicit-numeric-conversions-table.md)
- [<span data-ttu-id="1bc21-130">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="1bc21-130">Explicit Numeric Conversions Table</span></span>](./explicit-numeric-conversions-table.md)
