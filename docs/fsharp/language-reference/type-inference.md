---
title: Inferenza di tipi
description: Informazioni su come il F# compilatore deduce i tipi di valori, le variabili, parametri e valori restituiti.
ms.date: 05/16/2016
ms.openlocfilehash: 3e61d5c81fde0a48af66a47745123a842dc04cb1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666235"
---
# <a name="type-inference"></a><span data-ttu-id="dcb76-103">Inferenza di tipi</span><span class="sxs-lookup"><span data-stu-id="dcb76-103">Type Inference</span></span>

<span data-ttu-id="dcb76-104">Questo argomento viene descritto come il F# compilatore deduce i tipi di valori, le variabili, parametri e valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="dcb76-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="dcb76-105">L'inferenza del tipo in generale</span><span class="sxs-lookup"><span data-stu-id="dcb76-105">Type Inference in General</span></span>

<span data-ttu-id="dcb76-106">L'idea di inferenza del tipo è che non è necessario specificare i tipi di F# costrutti, ad eccezione di quando il compilatore conseguenze lampanti non è possibile dedurre il tipo.</span><span class="sxs-lookup"><span data-stu-id="dcb76-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="dcb76-107">L'omissione di informazioni sui tipi espliciti non significa che F# è un linguaggio tipizzato in modo dinamico o che i valori F# sono debolmente tipizzata.</span><span class="sxs-lookup"><span data-stu-id="dcb76-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="dcb76-108">F#è un linguaggio tipizzato in modo statico, il che significa che il compilatore deduce un tipo esatto di ogni costrutto durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="dcb76-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="dcb76-109">Se non esiste informazioni sufficienti per consentire al compilatore di dedurre i tipi di ogni costrutto, è necessario fornire informazioni aggiuntive sui tipi, in genere mediante l'aggiunta di annotazioni del tipo esplicito in una posizione nel codice.</span><span class="sxs-lookup"><span data-stu-id="dcb76-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>

## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="dcb76-110">Inferenza di tipi restituiti e parametri</span><span class="sxs-lookup"><span data-stu-id="dcb76-110">Inference of Parameter and Return Types</span></span>

<span data-ttu-id="dcb76-111">In un elenco di parametri, non è necessario specificare il tipo di ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="dcb76-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="dcb76-112">E ancora, F# è un linguaggio tipizzato in modo statico e pertanto ogni valore e l'espressione ha un tipo definito in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="dcb76-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="dcb76-113">Per i tipi che non si specifica in modo esplicito, il compilatore deduce il tipo in base al contesto.</span><span class="sxs-lookup"><span data-stu-id="dcb76-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="dcb76-114">Se il tipo non è in caso contrario specificato, si viene dedotto come generici.</span><span class="sxs-lookup"><span data-stu-id="dcb76-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="dcb76-115">Se il codice Usa un valore in modo incoerente, in modo che non è disponibile un unico tipo derivato che soddisfi tutti gli usi di un valore, che il compilatore segnala un errore.</span><span class="sxs-lookup"><span data-stu-id="dcb76-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="dcb76-116">Il tipo restituito di una funzione è determinato dal tipo dell'ultima espressione nella funzione.</span><span class="sxs-lookup"><span data-stu-id="dcb76-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="dcb76-117">Ad esempio, nel codice seguente, i tipi di parametro `a` e `b` e il tipo restituito vengono tutti considerati `int` perché il valore letterale `100` JE typu `int`.</span><span class="sxs-lookup"><span data-stu-id="dcb76-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="dcb76-118">È possibile influenzare l'inferenza del tipo modificando i valori letterali.</span><span class="sxs-lookup"><span data-stu-id="dcb76-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="dcb76-119">Se si apportano le `100` una `uint32` aggiungendo il suffisso `u`, i tipi di `a`, `b`, e il valore restituito sono considerati come `uint32`.</span><span class="sxs-lookup"><span data-stu-id="dcb76-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="dcb76-120">È anche possibile influenzare l'inferenza del tipo tramite altri costrutti che implicano le restrizioni sul tipo, ad esempio le funzioni e metodi che funzionano con solo un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="dcb76-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="dcb76-121">Inoltre, è possibile applicare le annotazioni di tipo espliciti per i parametri di metodo o una funzione o per le variabili nelle espressioni, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="dcb76-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="dcb76-122">Se si verificano conflitti tra i diversi vincoli generati errori.</span><span class="sxs-lookup"><span data-stu-id="dcb76-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="dcb76-123">È possibile specificare il valore restituito di una funzione in modo esplicito fornendo un'annotazione di tipo dopo che tutti i parametri.</span><span class="sxs-lookup"><span data-stu-id="dcb76-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="dcb76-124">Un caso comune in cui è utile in un parametro di un'annotazione di tipo è quando il parametro è un tipo di oggetto e si vuole usare un membro.</span><span class="sxs-lookup"><span data-stu-id="dcb76-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a><span data-ttu-id="dcb76-125">Generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="dcb76-125">Automatic Generalization</span></span>

<span data-ttu-id="dcb76-126">Se il codice della funzione non dipende dal tipo di un parametro, il compilatore considera il parametro generico.</span><span class="sxs-lookup"><span data-stu-id="dcb76-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="dcb76-127">Questa operazione viene definita *generalizzazione automatica*, e può essere molto utile per la scrittura di codice generico senza aumentare la complessità.</span><span class="sxs-lookup"><span data-stu-id="dcb76-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="dcb76-128">Ad esempio, la funzione seguente combina due parametri di qualsiasi tipo in una tupla.</span><span class="sxs-lookup"><span data-stu-id="dcb76-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="dcb76-129">Il tipo viene dedotto per essere</span><span class="sxs-lookup"><span data-stu-id="dcb76-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="dcb76-130">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="dcb76-130">Additional Information</span></span>

<span data-ttu-id="dcb76-131">L'inferenza del tipo è descritto più dettagliatamente il F# specifica del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="dcb76-131">Type inference is described in more detail in the F# Language Specification.</span></span>

## <a name="see-also"></a><span data-ttu-id="dcb76-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcb76-132">See also</span></span>

- [<span data-ttu-id="dcb76-133">Generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="dcb76-133">Automatic Generalization</span></span>](generics/automatic-generalization.md)