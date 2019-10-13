---
title: '! ( C# riferimento a null) (operatore)'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: cf941e5e3fa3fc6313ef8b2ff5c176aec68c1e6b
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291725"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="d244b-103">!</span><span class="sxs-lookup"><span data-stu-id="d244b-103">!</span></span> <span data-ttu-id="d244b-104">operatore (riferimento null) (C# riferimento)</span><span class="sxs-lookup"><span data-stu-id="d244b-104">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="d244b-105">Disponibile in C# 8,0 e versioni successive, il suffisso unario `!` operatore è l'operatore che perdona i valori null.</span><span class="sxs-lookup"><span data-stu-id="d244b-105">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="d244b-106">In un [contesto di annotazione Nullable](../../nullable-references.md#nullable-annotation-context)abilitato, è possibile usare l'operatore con indulgenza null per dichiarare che l'espressione `x` di un tipo di riferimento non è null: `x!`.</span><span class="sxs-lookup"><span data-stu-id="d244b-106">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't null: `x!`.</span></span> <span data-ttu-id="d244b-107">Il prefisso unario @no__t operatore-0 è un [operatore logico di negazione](boolean-logical-operators.md#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="d244b-107">The unary prefix `!` operator is a [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="d244b-108">L'operatore che perdona i valori null non ha alcun effetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d244b-108">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="d244b-109">Influisce solo sull'analisi del flusso statico del compilatore modificando lo stato null dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="d244b-109">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="d244b-110">In fase di esecuzione l'espressione `x!` restituisce il risultato dell'espressione sottostante `x`.</span><span class="sxs-lookup"><span data-stu-id="d244b-110">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

<span data-ttu-id="d244b-111">Per ulteriori informazioni sulla funzionalità dei tipi di riferimento Nullable, vedere [tipi di riferimento Nullable](../../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="d244b-111">For more information about the nullable reference types feature, see [Nullable reference types](../../nullable-references.md).</span></span>

## <a name="examples"></a><span data-ttu-id="d244b-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="d244b-112">Examples</span></span>

<span data-ttu-id="d244b-113">Uno dei casi d'uso dell'operatore che perdona i valori null è il test della logica di convalida degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="d244b-113">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="d244b-114">Si consideri ad esempio la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="d244b-114">For example, consider the following class:</span></span>

[!code-csharp[Person class](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="d244b-115">Usando il [Framework di test di MSTest](../../../core/testing/unit-testing-with-mstest.md), è possibile creare il test seguente per la logica di convalida nel costruttore:</span><span class="sxs-lookup"><span data-stu-id="d244b-115">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="d244b-116">Senza l'operatore di indulgenza null, il compilatore genera l'avviso seguente per il codice precedente: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span><span class="sxs-lookup"><span data-stu-id="d244b-116">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="d244b-117">Con l'uso dell'operatore di indulgenza null, si consente al compilatore di sapere che il passaggio di `null` è previsto e non deve essere avvisato.</span><span class="sxs-lookup"><span data-stu-id="d244b-117">With the use of the null-forgiving operator, you let the compiler know that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="d244b-118">È anche possibile usare l'operatore di indulgenza null quando si è certi che un'espressione non può essere `null`, ma il compilatore non riesce a conoscerlo.</span><span class="sxs-lookup"><span data-stu-id="d244b-118">You also can use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="d244b-119">Nell'esempio seguente, se il metodo `IsValid` restituisce `true`, il relativo argomento non è `null` ed è possibile dereferenziarlo in modo sicuro:</span><span class="sxs-lookup"><span data-stu-id="d244b-119">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="d244b-120">Senza l'operatore di indulgenza null, il compilatore genera l'avviso seguente per il codice `p.Name`: `Warning CS8602: Dereference of a possibly null reference.`.</span><span class="sxs-lookup"><span data-stu-id="d244b-120">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference.`.</span></span>

<span data-ttu-id="d244b-121">Se è possibile modificare il metodo `IsValid`, è possibile usare l'attributo [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) per indicare al compilatore che un argomento del metodo `IsValid` non può essere `null` quando il metodo restituisce `true`:</span><span class="sxs-lookup"><span data-stu-id="d244b-121">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to let the compiler know that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="d244b-122">Nell'esempio precedente non è necessario usare l'operatore che perdona i valori null perché il compilatore dispone di informazioni sufficienti per scoprire che `p` non può essere `null` nell'istruzione `if`.</span><span class="sxs-lookup"><span data-stu-id="d244b-122">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="d244b-123">Per ulteriori informazioni sugli attributi che consentono di specificare informazioni aggiuntive sullo stato null di una variabile, vedere [aggiornare le API con attributi per definire le aspettative null](../../nullable-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="d244b-123">For more information about the attributes that allow you to specify additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../../nullable-attributes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d244b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d244b-124">See also</span></span>

- [<span data-ttu-id="d244b-125">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="d244b-125">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d244b-126">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="d244b-126">C# operators</span></span>](index.md)
- <span data-ttu-id="d244b-127">[Esercitazione: Progettazione con tipi di riferimento Nullable @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="d244b-127">[Tutorial: Design with nullable reference types](../../tutorials/nullable-reference-types.md)</span></span>
