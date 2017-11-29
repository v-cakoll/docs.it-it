---
title: Tipi di eccezione (F#)
description: 'Informazioni su come definire e utilizzare i tipi di eccezione F #.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e850205a-b8da-459e-8f6d-cb3510f8f173
ms.openlocfilehash: a0864218841396c0ebdf26c7585e0e5bb778f83e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="exception-types"></a><span data-ttu-id="4aa85-104">Tipi di eccezione</span><span class="sxs-lookup"><span data-stu-id="4aa85-104">Exception Types</span></span>

<span data-ttu-id="4aa85-105">Esistono due categorie di eccezioni in F #: tipi di eccezione .NET e i tipi di eccezione F #.</span><span class="sxs-lookup"><span data-stu-id="4aa85-105">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="4aa85-106">In questo argomento viene descritto come definire e utilizzare i tipi di eccezione F #.</span><span class="sxs-lookup"><span data-stu-id="4aa85-106">This topic describes how to define and use F# exception types.</span></span>


## <a name="syntax"></a><span data-ttu-id="4aa85-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4aa85-107">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="4aa85-108">Note</span><span class="sxs-lookup"><span data-stu-id="4aa85-108">Remarks</span></span>
<span data-ttu-id="4aa85-109">Nella sintassi precedente, *-tipo di eccezione* è il nome di un nuovo tipo, eccezione F # e *-tipo di argomento* rappresenta il tipo di un argomento che può essere fornito quando si genera un'eccezione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="4aa85-109">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="4aa85-110">È possibile specificare più argomenti usando un tipo di tupla per *-tipo di argomento*.</span><span class="sxs-lookup"><span data-stu-id="4aa85-110">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="4aa85-111">Una definizione tipiche per un'eccezione F # è simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="4aa85-111">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="4aa85-112">È possibile generare un'eccezione di questo tipo utilizzando il `raise` funzione, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4aa85-112">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="4aa85-113">È possibile utilizzare un tipo di eccezione F # direttamente nei filtri in un `try...with` espressione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4aa85-113">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="4aa85-114">Il tipo di eccezione definito con il `exception` la parola chiave in F # è un nuovo tipo che eredita da `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="4aa85-114">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>


## <a name="see-also"></a><span data-ttu-id="4aa85-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4aa85-115">See Also</span></span>
[<span data-ttu-id="4aa85-116">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="4aa85-116">Exception Handling</span></span>](index.md)

[<span data-ttu-id="4aa85-117">Eccezioni: funzione `raise`</span><span class="sxs-lookup"><span data-stu-id="4aa85-117">Exceptions: the `raise` Function</span></span>](the-raise-function.md)

[<span data-ttu-id="4aa85-118">Gerarchia delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="4aa85-118">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
