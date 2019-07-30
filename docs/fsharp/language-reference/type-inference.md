---
title: Inferenza di tipi
description: Informazioni sul modo F# in cui il compilatore deduce i tipi di valori, variabili, parametri e valori restituiti.
ms.date: 05/16/2016
ms.openlocfilehash: 4b18c1a67a8b7ddadb4fb334ea4736e9fd29feb0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630191"
---
# <a name="type-inference"></a><span data-ttu-id="b25c9-103">Inferenza di tipi</span><span class="sxs-lookup"><span data-stu-id="b25c9-103">Type Inference</span></span>

<span data-ttu-id="b25c9-104">In questo argomento viene descritto F# il modo in cui il compilatore deduce i tipi di valori, variabili, parametri e valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="b25c9-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="b25c9-105">Inferenza del tipo in generale</span><span class="sxs-lookup"><span data-stu-id="b25c9-105">Type Inference in General</span></span>

<span data-ttu-id="b25c9-106">Il concetto di inferenza del tipo è che non è necessario specificare i tipi di F# costrutti tranne quando il compilatore non può dedurre definitivamente il tipo.</span><span class="sxs-lookup"><span data-stu-id="b25c9-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="b25c9-107">Omettendo le informazioni sul tipo esplicito non significa F# che è un linguaggio tipizzato in modo dinamico o F# che i valori in sono debolmente tipizzati.</span><span class="sxs-lookup"><span data-stu-id="b25c9-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="b25c9-108">F#è un linguaggio tipizzato in modo statico, ovvero il compilatore deduce un tipo esatto per ogni costrutto durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="b25c9-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="b25c9-109">Se non sono disponibili informazioni sufficienti per consentire al compilatore di dedurre i tipi di ogni costrutto, è necessario fornire informazioni sui tipi aggiuntive, in genere aggiungendo annotazioni di tipo esplicite in un punto qualsiasi del codice.</span><span class="sxs-lookup"><span data-stu-id="b25c9-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>

## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="b25c9-110">Inferenza dei tipi Parameter e Return</span><span class="sxs-lookup"><span data-stu-id="b25c9-110">Inference of Parameter and Return Types</span></span>

<span data-ttu-id="b25c9-111">In un elenco di parametri non è necessario specificare il tipo di ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="b25c9-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="b25c9-112">F# È ancora un linguaggio tipizzato in modo statico, pertanto ogni valore ed espressione ha un tipo definito in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="b25c9-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="b25c9-113">Per i tipi non specificati in modo esplicito, il compilatore deduce il tipo in base al contesto.</span><span class="sxs-lookup"><span data-stu-id="b25c9-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="b25c9-114">Se il tipo non è specificato diversamente, viene dedotto come generico.</span><span class="sxs-lookup"><span data-stu-id="b25c9-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="b25c9-115">Se il codice usa un valore in modo incoerente, in modo che non esistano singoli tipi dedotti che soddisfino tutti gli usi di un valore, il compilatore segnala un errore.</span><span class="sxs-lookup"><span data-stu-id="b25c9-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="b25c9-116">Il tipo restituito di una funzione è determinato dal tipo dell'ultima espressione nella funzione.</span><span class="sxs-lookup"><span data-stu-id="b25c9-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="b25c9-117">Nel codice seguente, ad `a` esempio, i tipi di `int` parametro e `b` e il tipo restituito sono tutti dedotti perché il valore letterale `100` è di tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="b25c9-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="b25c9-118">È possibile influenzare l'inferenza del tipo modificando i valori letterali.</span><span class="sxs-lookup"><span data-stu-id="b25c9-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="b25c9-119">Se si imposta l' `100` oggetto `uint32` accodando il suffisso `u`, i tipi di `a`, `b`e il valore restituito vengono dedotti come `uint32`.</span><span class="sxs-lookup"><span data-stu-id="b25c9-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="b25c9-120">È anche possibile influenzare l'inferenza del tipo usando altri costrutti che implicano restrizioni sul tipo, ad esempio funzioni e metodi che funzionano solo con un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="b25c9-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="b25c9-121">Inoltre, è possibile applicare annotazioni di tipo esplicito a parametri di funzione o di metodo o a variabili nelle espressioni, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="b25c9-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="b25c9-122">Gli errori risultano se si verificano conflitti tra vincoli diversi.</span><span class="sxs-lookup"><span data-stu-id="b25c9-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="b25c9-123">È anche possibile specificare in modo esplicito il valore restituito di una funzione fornendo un'annotazione di tipo dopo tutti i parametri.</span><span class="sxs-lookup"><span data-stu-id="b25c9-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="b25c9-124">Un caso comune in cui un'annotazione del tipo è utile per un parametro è quando il parametro è un tipo di oggetto e si vuole usare un membro.</span><span class="sxs-lookup"><span data-stu-id="b25c9-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a><span data-ttu-id="b25c9-125">Generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="b25c9-125">Automatic Generalization</span></span>

<span data-ttu-id="b25c9-126">Se il codice della funzione non dipende dal tipo di un parametro, il compilatore considera il parametro come generico.</span><span class="sxs-lookup"><span data-stu-id="b25c9-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="b25c9-127">Questa operazione è detta *generalizzazione automatica*e può essere un potente strumento per scrivere codice generico senza aumentare la complessità.</span><span class="sxs-lookup"><span data-stu-id="b25c9-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="b25c9-128">La funzione seguente, ad esempio, combina due parametri di qualsiasi tipo in una tupla.</span><span class="sxs-lookup"><span data-stu-id="b25c9-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="b25c9-129">Il tipo viene dedotto come</span><span class="sxs-lookup"><span data-stu-id="b25c9-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="b25c9-130">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b25c9-130">Additional Information</span></span>

<span data-ttu-id="b25c9-131">L'inferenza del tipo è descritta più dettagliatamente nella specifica del F# linguaggio.</span><span class="sxs-lookup"><span data-stu-id="b25c9-131">Type inference is described in more detail in the F# Language Specification.</span></span>

## <a name="see-also"></a><span data-ttu-id="b25c9-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b25c9-132">See also</span></span>

- [<span data-ttu-id="b25c9-133">Generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="b25c9-133">Automatic Generalization</span></span>](./generics/automatic-generalization.md)
