---
title: '! operatore (null-perdonatore)-riferimenti per C#'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 772f37f1fc7446eae66f0cd0f12adb5e2e41997d
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595949"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="956fd-103">!</span><span class="sxs-lookup"><span data-stu-id="956fd-103">!</span></span> <span data-ttu-id="956fd-104">operatore (null-perdonatore) (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="956fd-104">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="956fd-105">Disponibile in C# 8,0 e versioni successive, l'operatore `!` unario di suffisso è l'operatore che perdona i valori null.</span><span class="sxs-lookup"><span data-stu-id="956fd-105">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="956fd-106">In un [contesto di annotazione Nullable](../../nullable-references.md#nullable-annotation-context)abilitato, si usa l'operatore che perdona i valori `x` null per dichiarare che l' `null`espressione `x!`di un tipo di riferimento non è:.</span><span class="sxs-lookup"><span data-stu-id="956fd-106">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't `null`: `x!`.</span></span> <span data-ttu-id="956fd-107">L'operatore di `!` prefisso unario è l' [operatore logico di negazione](boolean-logical-operators.md#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="956fd-107">The unary prefix `!` operator is the [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="956fd-108">L'operatore che perdona i valori null non ha alcun effetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="956fd-108">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="956fd-109">Influisce solo sull'analisi del flusso statico del compilatore modificando lo stato null dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="956fd-109">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="956fd-110">In fase di esecuzione, `x!` l'espressione restituisce il risultato dell'espressione `x`sottostante.</span><span class="sxs-lookup"><span data-stu-id="956fd-110">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

> [!NOTE]
> <span data-ttu-id="956fd-111">In C# 8 l'operatore che perdona i valori null interagisce con gli [operatori condizionali null](member-access-operators.md#null-conditional-operators--and-) in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="956fd-111">In C# 8 the null-forgiving operator interacts with the [null-conditional operators](member-access-operators.md#null-conditional-operators--and-) in an unexpected way.</span></span> <span data-ttu-id="956fd-112">L'espressione `x?.y!.z` viene analizzata come `(x?.y)!.z`.</span><span class="sxs-lookup"><span data-stu-id="956fd-112">The expression `x?.y!.z` is parsed as `(x?.y)!.z`.</span></span> <span data-ttu-id="956fd-113">A causa di questa `z` interpretazione viene valutata `x` anche `null`se è, che può produrre <xref:System.NullReferenceException>un.</span><span class="sxs-lookup"><span data-stu-id="956fd-113">Due to this interpretation `z` is evaluated even if `x` is `null`, which may result in a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="956fd-114">Per ulteriori informazioni sulla funzionalità dei tipi di riferimento Nullable, vedere [tipi di riferimento Nullable](../builtin-types/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="956fd-114">For more information about the nullable reference types feature, see [Nullable reference types](../builtin-types/nullable-reference-types.md).</span></span>

## <a name="examples"></a><span data-ttu-id="956fd-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="956fd-115">Examples</span></span>

<span data-ttu-id="956fd-116">Uno dei casi d'uso dell'operatore che perdona i valori null è il test della logica di convalida degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="956fd-116">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="956fd-117">Si consideri ad esempio la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="956fd-117">For example, consider the following class:</span></span>

[!code-csharp[Person class](snippets/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="956fd-118">Usando il [Framework di test di MSTest](../../../core/testing/unit-testing-with-mstest.md), è possibile creare il test seguente per la logica di convalida nel costruttore:</span><span class="sxs-lookup"><span data-stu-id="956fd-118">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](snippets/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="956fd-119">Senza l'operatore di indulgenza null, il compilatore genera l'avviso seguente per il codice precedente `Warning CS8625: Cannot convert null literal to non-nullable reference type`:.</span><span class="sxs-lookup"><span data-stu-id="956fd-119">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="956fd-120">Utilizzando l'operatore di indulgenza null, si informa il compilatore che il `null` passaggio è previsto e non deve essere avvisato.</span><span class="sxs-lookup"><span data-stu-id="956fd-120">By using the null-forgiving operator, you inform the compiler that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="956fd-121">È anche possibile usare l'operatore di indulgenza null quando si è certi che un'espressione non `null` può essere, ma il compilatore non riesce a riconoscerlo.</span><span class="sxs-lookup"><span data-stu-id="956fd-121">You can also use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="956fd-122">Nell'esempio seguente, se il `IsValid` metodo restituisce `true`, il relativo argomento non `null` è ed è possibile dereferenziarlo in modo sicuro:</span><span class="sxs-lookup"><span data-stu-id="956fd-122">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](snippets/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="956fd-123">Senza l'operatore di indulgenza null, il compilatore genera l'avviso seguente per `p.Name` il codice `Warning CS8602: Dereference of a possibly null reference`:.</span><span class="sxs-lookup"><span data-stu-id="956fd-123">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference`.</span></span>

<span data-ttu-id="956fd-124">Se è possibile modificare il `IsValid` metodo, è possibile usare l'attributo [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) per informare il compilatore che un argomento del `IsValid` metodo non può essere `null` quando il metodo restituisce `true`:</span><span class="sxs-lookup"><span data-stu-id="956fd-124">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to inform the compiler that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](snippets/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="956fd-125">Nell'esempio precedente non è necessario usare l'operatore che perdona i valori null perché il compilatore dispone di informazioni sufficienti per individuare che `p` non possono essere `null` incluse nell' `if` istruzione.</span><span class="sxs-lookup"><span data-stu-id="956fd-125">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="956fd-126">Per ulteriori informazioni sugli attributi che consentono di fornire informazioni aggiuntive sullo stato null di una variabile, vedere [aggiornare le API con attributi per definire le aspettative null](../attributes/nullable-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="956fd-126">For more information about the attributes that allow you to provide additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../attributes/nullable-analysis.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="956fd-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="956fd-127">C# language specification</span></span>

<span data-ttu-id="956fd-128">Per ulteriori informazioni, vedere [la sezione operatore con indulgenza null](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) della [bozza della specifica dei tipi di riferimento Nullable](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span><span class="sxs-lookup"><span data-stu-id="956fd-128">For more information, see [The null-forgiving operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) section of the [draft of the nullable reference types specification](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="956fd-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="956fd-129">See also</span></span>

- [<span data-ttu-id="956fd-130">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="956fd-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="956fd-131">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="956fd-131">C# operators</span></span>](index.md)
- [<span data-ttu-id="956fd-132">Esercitazione: progettare con tipi di riferimento Nullable</span><span class="sxs-lookup"><span data-stu-id="956fd-132">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
