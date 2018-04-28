---
title: Inferenza del tipo (F#)
description: 'Informazioni su come il compilatore F # deduce i tipi di valori, variabili, parametri e valori restituiti.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: b5f7861c0a638baebfe72c9b4cf7dca119339ae3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="type-inference"></a><span data-ttu-id="de11c-103">Inferenza di tipi</span><span class="sxs-lookup"><span data-stu-id="de11c-103">Type Inference</span></span>

<span data-ttu-id="de11c-104">In questo argomento viene descritto come il compilatore F # deduce i tipi di valori, variabili, parametri e valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="de11c-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="de11c-105">L'inferenza del tipo in generale</span><span class="sxs-lookup"><span data-stu-id="de11c-105">Type Inference in General</span></span>
<span data-ttu-id="de11c-106">L'idea di inferenza del tipo è che non è necessario specificare i tipi di costrutti di F #, ad eccezione di quando il compilatore non non è possibile dedurre il tipo.</span><span class="sxs-lookup"><span data-stu-id="de11c-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="de11c-107">L'omissione di informazioni di tipo esplicito non significa che F # è un linguaggio tipizzato in modo dinamico o che i valori in F # sono debolmente tipizzata.</span><span class="sxs-lookup"><span data-stu-id="de11c-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="de11c-108">F # è un linguaggio tipizzato in modo statico, il che significa che il compilatore deduce un tipo esatto di ogni costrutto durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="de11c-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="de11c-109">Se non sono informazioni sufficienti per consentire al compilatore di dedurre i tipi di ogni costrutto, è necessario fornire informazioni aggiuntive sul tipo, in genere mediante l'aggiunta di annotazioni di tipo esplicita in un punto nel codice.</span><span class="sxs-lookup"><span data-stu-id="de11c-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>


## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="de11c-110">Inferenza di tipi restituiti e parametri</span><span class="sxs-lookup"><span data-stu-id="de11c-110">Inference of Parameter and Return Types</span></span>
<span data-ttu-id="de11c-111">In un elenco di parametri, non si dispone di specificare il tipo di ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="de11c-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="de11c-112">Ancora, F # è un linguaggio tipizzato in modo statico e pertanto ogni valore e l'espressione con un tipo definito in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="de11c-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="de11c-113">Per i tipi che non si specifica in modo esplicito, il compilatore deduce il tipo in base al contesto.</span><span class="sxs-lookup"><span data-stu-id="de11c-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="de11c-114">Se il tipo non è specificata, viene dedotta generico.</span><span class="sxs-lookup"><span data-stu-id="de11c-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="de11c-115">Se il codice utilizza un valore in modo incoerente, in modo che non è disponibile un unico tipo dedotto che soddisfi tutti gli usi di un valore, che il compilatore segnala un errore.</span><span class="sxs-lookup"><span data-stu-id="de11c-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="de11c-116">Il tipo restituito di una funzione è determinato dal tipo dell'ultima espressione nella funzione.</span><span class="sxs-lookup"><span data-stu-id="de11c-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="de11c-117">Ad esempio, nel codice seguente, i tipi di parametro `a` e `b` e il tipo restituito sono considerati come `int` perché il valore letterale `100` è di tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="de11c-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="de11c-118">È possibile influenzare l'inferenza del tipo modificando i valori letterali.</span><span class="sxs-lookup"><span data-stu-id="de11c-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="de11c-119">Se si apportano le `100` un `uint32` aggiungendo il suffisso `u`, i tipi di `a`, `b`, e il valore restituito sono considerati come `uint32`.</span><span class="sxs-lookup"><span data-stu-id="de11c-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="de11c-120">È anche possibile influenzare l'inferenza del tipo utilizzando altri costrutti che comportano restrizioni relative al tipo, ad esempio le funzioni e metodi che funzionano con solo un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="de11c-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="de11c-121">Inoltre, è possibile applicare le annotazioni di tipo esplicito per i parametri di funzione o un metodo o per le variabili nelle espressioni, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="de11c-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="de11c-122">Verificarsi errori se si verificano conflitti tra i diversi vincoli.</span><span class="sxs-lookup"><span data-stu-id="de11c-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="de11c-123">Anche in modo esplicito, è possibile specificare il valore restituito di una funzione, fornendo un'annotazione di tipo dopo che tutti i parametri.</span><span class="sxs-lookup"><span data-stu-id="de11c-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="de11c-124">Un caso comune in cui è utile in un parametro di un'annotazione di tipo è quando il parametro è un tipo di oggetto e si desidera utilizzare un membro.</span><span class="sxs-lookup"><span data-stu-id="de11c-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]
    
## <a name="automatic-generalization"></a><span data-ttu-id="de11c-125">Generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="de11c-125">Automatic Generalization</span></span>
<span data-ttu-id="de11c-126">Se il codice della funzione non dipende dal tipo di un parametro, il compilatore considera il parametro generico.</span><span class="sxs-lookup"><span data-stu-id="de11c-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="de11c-127">Si tratta di *generalizzazione automatica*, e può essere molto utile per scrivere codice generico senza aumentare la complessità.</span><span class="sxs-lookup"><span data-stu-id="de11c-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="de11c-128">Ad esempio, la funzione seguente combina due parametri di qualsiasi tipo in una tupla.</span><span class="sxs-lookup"><span data-stu-id="de11c-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="de11c-129">Il tipo viene dedotto da</span><span class="sxs-lookup"><span data-stu-id="de11c-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="de11c-130">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="de11c-130">Additional Information</span></span>
<span data-ttu-id="de11c-131">L'inferenza del tipo è descritto in dettaglio nella specifica del linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="de11c-131">Type inference is described in more detail in the F# Language Specification.</span></span>


## <a name="see-also"></a><span data-ttu-id="de11c-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de11c-132">See Also</span></span>
[<span data-ttu-id="de11c-133">Generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="de11c-133">Automatic Generalization</span></span>](generics/automatic-generalization.md)
