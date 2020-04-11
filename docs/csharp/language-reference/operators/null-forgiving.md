---
title: '! (null-forgiving) (operatore - Riferimento in C'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 658043f8d5e149064f6da328657b2ccef9b5da94
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121439"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="ef35b-103">!</span><span class="sxs-lookup"><span data-stu-id="ef35b-103">!</span></span> <span data-ttu-id="ef35b-104">(null-forgiving) (riferimento c'è)</span><span class="sxs-lookup"><span data-stu-id="ef35b-104">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="ef35b-105">Disponibile in C , 8.0 e versioni `!` successive, l'operatore suffisso unario è l'operatore per dono null.</span><span class="sxs-lookup"><span data-stu-id="ef35b-105">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="ef35b-106">In un contesto di [annotazione nullable](../../nullable-references.md#nullable-annotation-context)abilitato , utilizzare `x` l'operatore di `null` `x!`perdono null per dichiarare che l'espressione di un tipo di riferimento non è : .</span><span class="sxs-lookup"><span data-stu-id="ef35b-106">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't `null`: `x!`.</span></span> <span data-ttu-id="ef35b-107">L'operatore `!` prefisso unario è l'operatore di [negazione logica.](boolean-logical-operators.md#logical-negation-operator-)</span><span class="sxs-lookup"><span data-stu-id="ef35b-107">The unary prefix `!` operator is the [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="ef35b-108">L'operatore che perdona i valori Null non ha alcun effetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ef35b-108">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="ef35b-109">Influisce solo sull'analisi statica del flusso del compilatore modificando lo stato null dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="ef35b-109">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="ef35b-110">In fase di `x!` esecuzione, expression restituisce `x`il risultato dell'espressione sottostante.</span><span class="sxs-lookup"><span data-stu-id="ef35b-110">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

<span data-ttu-id="ef35b-111">Per ulteriori informazioni sulla funzionalità dei tipi di riferimento nullable, vedere [Tipi di riferimento nullable](../builtin-types/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="ef35b-111">For more information about the nullable reference types feature, see [Nullable reference types](../builtin-types/nullable-reference-types.md).</span></span>

## <a name="examples"></a><span data-ttu-id="ef35b-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="ef35b-112">Examples</span></span>

<span data-ttu-id="ef35b-113">Uno dei casi d'uso dell'operatore che perdona i valori Null è nel test della logica di convalida dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="ef35b-113">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="ef35b-114">Si consideri ad esempio la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="ef35b-114">For example, consider the following class:</span></span>

[!code-csharp[Person class](snippets/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="ef35b-115">Utilizzando il framework di [test MSTest](../../../core/testing/unit-testing-with-mstest.md), è possibile creare il test seguente per la logica di convalida nel costruttore:</span><span class="sxs-lookup"><span data-stu-id="ef35b-115">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](snippets/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="ef35b-116">Senza l'operatore di perdono null, il compilatore `Warning CS8625: Cannot convert null literal to non-nullable reference type`genera il seguente avviso per il codice precedente: .</span><span class="sxs-lookup"><span data-stu-id="ef35b-116">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="ef35b-117">Utilizzando l'operatore di perdono null, `null` si informa il compilatore che il passaggio è previsto e non deve essere avvisato.</span><span class="sxs-lookup"><span data-stu-id="ef35b-117">By using the null-forgiving operator, you inform the compiler that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="ef35b-118">È anche possibile usare l'operatore di perdono null `null` quando si sa sicuramente che un'espressione non può essere, ma il compilatore non riesce a riconoscerlo.</span><span class="sxs-lookup"><span data-stu-id="ef35b-118">You also can use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="ef35b-119">Nell'esempio seguente, `IsValid` se `true`il metodo restituisce , il relativo argomento non `null` è ed è possibile dereferenziarlo in modo sicuro:</span><span class="sxs-lookup"><span data-stu-id="ef35b-119">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](snippets/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="ef35b-120">Senza l'operatore di perdono null, il `p.Name` compilatore genera il seguente avviso per il codice: `Warning CS8602: Dereference of a possibly null reference`.</span><span class="sxs-lookup"><span data-stu-id="ef35b-120">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference`.</span></span>

<span data-ttu-id="ef35b-121">Se è possibile `IsValid` modificare il metodo, è possibile utilizzare l'attributo [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) per informare il compilatore che un argomento del `IsValid` metodo non può essere `null` quando il metodo restituisce `true`:</span><span class="sxs-lookup"><span data-stu-id="ef35b-121">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to inform the compiler that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](snippets/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="ef35b-122">Nell'esempio precedente, non è necessario utilizzare l'operatore di perdono null perché `p` il `null` compilatore `if` dispone di informazioni sufficienti per scoprire che non possono essere all'interno dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="ef35b-122">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="ef35b-123">Per ulteriori informazioni sugli attributi che consentono di fornire informazioni aggiuntive sullo stato null di una variabile, vedere [Aggiornare le API con attributi per definire le aspettative null.](../../nullable-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="ef35b-123">For more information about the attributes that allow you to provide additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../../nullable-attributes.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ef35b-124">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="ef35b-124">C# language specification</span></span>

<span data-ttu-id="ef35b-125">Per ulteriori informazioni, vedere [Sezione relativa all'operatore](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) di perdono null della bozza della specifica dei tipi di riferimento [nullable](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span><span class="sxs-lookup"><span data-stu-id="ef35b-125">For more information, see [The null-forgiving operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) section of the [draft of the nullable reference types specification](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ef35b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef35b-126">See also</span></span>

- [<span data-ttu-id="ef35b-127">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="ef35b-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ef35b-128">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="ef35b-128">C# operators</span></span>](index.md)
- [<span data-ttu-id="ef35b-129">Esercitazione: Progettazione con tipi di riferimento nullableTutorial: Design with nullable reference types</span><span class="sxs-lookup"><span data-stu-id="ef35b-129">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
