---
title: '! operatore (null-perdonatore)-riferimenti per C#'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 2a8db2882968dbcbe6a8868ab6fe1c128c94a41f
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624878"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="a52c8-103">!</span><span class="sxs-lookup"><span data-stu-id="a52c8-103">!</span></span> <span data-ttu-id="a52c8-104">operatore (null-perdonatore) (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a52c8-104">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="a52c8-105">Disponibile in C# 8,0 e versioni successive, l'operatore `!` unario di suffisso è l'operatore che perdona i valori null.</span><span class="sxs-lookup"><span data-stu-id="a52c8-105">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="a52c8-106">In un [contesto di annotazione Nullable](../../nullable-references.md#nullable-annotation-context)abilitato, si usa l'operatore che perdona i valori `x` null per dichiarare che l' `null`espressione `x!`di un tipo di riferimento non è:.</span><span class="sxs-lookup"><span data-stu-id="a52c8-106">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't `null`: `x!`.</span></span> <span data-ttu-id="a52c8-107">L'operatore di `!` prefisso unario è l' [operatore logico di negazione](boolean-logical-operators.md#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="a52c8-107">The unary prefix `!` operator is the [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="a52c8-108">L'operatore che perdona i valori null non ha alcun effetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a52c8-108">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="a52c8-109">Influisce solo sull'analisi del flusso statico del compilatore modificando lo stato null dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="a52c8-109">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="a52c8-110">In fase di esecuzione, `x!` l'espressione restituisce il risultato dell'espressione `x`sottostante.</span><span class="sxs-lookup"><span data-stu-id="a52c8-110">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

> [!NOTE]
> <span data-ttu-id="a52c8-111">In C# 8, l'operatore che perdona i valori null termina l'elenco delle operazioni [condizionali null](member-access-operators.md#null-conditional-operators--and-) precedenti.</span><span class="sxs-lookup"><span data-stu-id="a52c8-111">In C# 8, the null-forgiving operator terminates the list of preceding [null-conditional](member-access-operators.md#null-conditional-operators--and-) operations.</span></span> <span data-ttu-id="a52c8-112">Ad esempio, l'espressione `x?.y!.z` viene analizzata come `(x?.y)!.z`.</span><span class="sxs-lookup"><span data-stu-id="a52c8-112">For example, the expression `x?.y!.z` is parsed as `(x?.y)!.z`.</span></span> <span data-ttu-id="a52c8-113">A causa di questa interpretazione `z` , viene valutato anche `x` se `null`è, che può produrre un <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="a52c8-113">Due to this interpretation, `z` is evaluated even if `x` is `null`, which may result in a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="a52c8-114">Per ulteriori informazioni sulla funzionalità dei tipi di riferimento Nullable, vedere [tipi di riferimento Nullable](../builtin-types/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="a52c8-114">For more information about the nullable reference types feature, see [Nullable reference types](../builtin-types/nullable-reference-types.md).</span></span>

## <a name="examples"></a><span data-ttu-id="a52c8-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="a52c8-115">Examples</span></span>

<span data-ttu-id="a52c8-116">Uno dei casi d'uso dell'operatore che perdona i valori null è il test della logica di convalida degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="a52c8-116">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="a52c8-117">Si consideri ad esempio la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="a52c8-117">For example, consider the following class:</span></span>

[!code-csharp[Person class](snippets/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="a52c8-118">Usando il [Framework di test di MSTest](../../../core/testing/unit-testing-with-mstest.md), è possibile creare il test seguente per la logica di convalida nel costruttore:</span><span class="sxs-lookup"><span data-stu-id="a52c8-118">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](snippets/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="a52c8-119">Senza l'operatore di indulgenza null, il compilatore genera l'avviso seguente per il codice precedente `Warning CS8625: Cannot convert null literal to non-nullable reference type`:.</span><span class="sxs-lookup"><span data-stu-id="a52c8-119">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="a52c8-120">Utilizzando l'operatore di indulgenza null, si informa il compilatore che il `null` passaggio è previsto e non deve essere avvisato.</span><span class="sxs-lookup"><span data-stu-id="a52c8-120">By using the null-forgiving operator, you inform the compiler that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="a52c8-121">È anche possibile usare l'operatore di indulgenza null quando si è certi che un'espressione non `null` può essere, ma il compilatore non riesce a riconoscerlo.</span><span class="sxs-lookup"><span data-stu-id="a52c8-121">You can also use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="a52c8-122">Nell'esempio seguente, se il `IsValid` metodo restituisce `true`, il relativo argomento non `null` è ed è possibile dereferenziarlo in modo sicuro:</span><span class="sxs-lookup"><span data-stu-id="a52c8-122">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](snippets/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="a52c8-123">Senza l'operatore di indulgenza null, il compilatore genera l'avviso seguente per `p.Name` il codice `Warning CS8602: Dereference of a possibly null reference`:.</span><span class="sxs-lookup"><span data-stu-id="a52c8-123">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference`.</span></span>

<span data-ttu-id="a52c8-124">Se è possibile modificare il `IsValid` metodo, è possibile usare l'attributo [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) per informare il compilatore che un argomento del `IsValid` metodo non può essere `null` quando il metodo restituisce `true`:</span><span class="sxs-lookup"><span data-stu-id="a52c8-124">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to inform the compiler that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](snippets/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="a52c8-125">Nell'esempio precedente non è necessario usare l'operatore che perdona i valori null perché il compilatore dispone di informazioni sufficienti per individuare che `p` non possono essere `null` incluse nell' `if` istruzione.</span><span class="sxs-lookup"><span data-stu-id="a52c8-125">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="a52c8-126">Per ulteriori informazioni sugli attributi che consentono di fornire informazioni aggiuntive sullo stato null di una variabile, vedere [aggiornare le API con attributi per definire le aspettative null](../attributes/nullable-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="a52c8-126">For more information about the attributes that allow you to provide additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../attributes/nullable-analysis.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a52c8-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a52c8-127">C# language specification</span></span>

<span data-ttu-id="a52c8-128">Per ulteriori informazioni, vedere [la sezione operatore con indulgenza null](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) della [bozza della specifica dei tipi di riferimento Nullable](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span><span class="sxs-lookup"><span data-stu-id="a52c8-128">For more information, see [The null-forgiving operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) section of the [draft of the nullable reference types specification](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a52c8-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a52c8-129">See also</span></span>

- [<span data-ttu-id="a52c8-130">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="a52c8-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a52c8-131">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="a52c8-131">C# operators</span></span>](index.md)
- [<span data-ttu-id="a52c8-132">Esercitazione: progettare con tipi di riferimento Nullable</span><span class="sxs-lookup"><span data-stu-id="a52c8-132">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
