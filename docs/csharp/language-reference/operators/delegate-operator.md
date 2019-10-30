---
title: Operatore delegate - Riferimenti per C#
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 9a78faaccffa9e7d4bf2829d8dfa0fa62a788bba
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039035"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="4e736-102">Operatore delegate (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4e736-102">delegate operator (C# reference)</span></span>

<span data-ttu-id="4e736-103">L'operatore `delegate` crea un metodo anonimo che può essere convertito in un tipo delegato:</span><span class="sxs-lookup"><span data-stu-id="4e736-103">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](~/samples/csharp/language-reference/operators/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="4e736-104">A partire C# da 3, le espressioni lambda forniscono un modo più conciso ed espressivo per creare una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="4e736-104">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="4e736-105">Usare l'[operatore =>](lambda-operator.md) per costruire un'espressione lambda:</span><span class="sxs-lookup"><span data-stu-id="4e736-105">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](~/samples/csharp/language-reference/operators/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="4e736-106">Per altre informazioni sulle funzionalità delle espressioni lambda, ad esempio l'acquisizione di variabili esterne, vedere [Espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4e736-106">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

<span data-ttu-id="4e736-107">Quando si usa l'operatore `delegate`, è possibile omettere l'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="4e736-107">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="4e736-108">In tal caso, il metodo anonimo creato può essere convertito in un tipo delegato con qualsiasi elenco di parametri, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4e736-108">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](~/samples/csharp/language-reference/operators/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="4e736-109">Questa è l'unica funzionalità di metodi anonimi non supportata dalle espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="4e736-109">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="4e736-110">In tutti gli altri casi, un'espressione lambda è la modalità preferita per scrivere codice inline.</span><span class="sxs-lookup"><span data-stu-id="4e736-110">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="4e736-111">È anche possibile usare la parola chiave `delegate` per dichiarare un [tipo delegato](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="4e736-111">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4e736-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="4e736-112">C# language specification</span></span>

<span data-ttu-id="4e736-113">Per altre informazioni, vedere la sezione [Espressioni di funzioni anonime](~/_csharplang/spec/expressions.md#anonymous-function-expressions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="4e736-113">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4e736-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e736-114">See also</span></span>

- [<span data-ttu-id="4e736-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="4e736-115">C# reference</span></span>](../index.md)
- [<span data-ttu-id="4e736-116">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="4e736-116">C# operators</span></span>](index.md)
- [<span data-ttu-id="4e736-117">= operatore ></span><span class="sxs-lookup"><span data-stu-id="4e736-117">=> operator</span></span>](lambda-operator.md)
