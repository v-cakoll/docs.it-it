---
title: Tipi di eccezione (F#)
description: 'Informazioni su come definire e utilizzare i tipi di eccezione F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 4462dd00ddf9524d1fd376ee1e73e81fcfd5d945
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564038"
---
# <a name="exception-types"></a><span data-ttu-id="8ee5b-103">Tipi di eccezione</span><span class="sxs-lookup"><span data-stu-id="8ee5b-103">Exception Types</span></span>

<span data-ttu-id="8ee5b-104">Esistono due categorie di eccezioni in F #: tipi di eccezione .NET e i tipi di eccezione F #.</span><span class="sxs-lookup"><span data-stu-id="8ee5b-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="8ee5b-105">In questo argomento viene descritto come definire e utilizzare i tipi di eccezione F #.</span><span class="sxs-lookup"><span data-stu-id="8ee5b-105">This topic describes how to define and use F# exception types.</span></span>


## <a name="syntax"></a><span data-ttu-id="8ee5b-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ee5b-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="8ee5b-107">Note</span><span class="sxs-lookup"><span data-stu-id="8ee5b-107">Remarks</span></span>
<span data-ttu-id="8ee5b-108">Nella sintassi precedente, *-tipo di eccezione* è il nome di un nuovo tipo, eccezione F # e *-tipo di argomento* rappresenta il tipo di un argomento che può essere fornito quando si genera un'eccezione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="8ee5b-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="8ee5b-109">È possibile specificare più argomenti usando un tipo di tupla per *-tipo di argomento*.</span><span class="sxs-lookup"><span data-stu-id="8ee5b-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="8ee5b-110">Una definizione tipiche per un'eccezione F # è simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="8ee5b-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="8ee5b-111">È possibile generare un'eccezione di questo tipo utilizzando il `raise` funzione, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8ee5b-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="8ee5b-112">È possibile utilizzare un tipo di eccezione F # direttamente nei filtri in un `try...with` espressione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8ee5b-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="8ee5b-113">Il tipo di eccezione definito con il `exception` la parola chiave in F # è un nuovo tipo che eredita da `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="8ee5b-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>


## <a name="see-also"></a><span data-ttu-id="8ee5b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ee5b-114">See Also</span></span>
[<span data-ttu-id="8ee5b-115">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="8ee5b-115">Exception Handling</span></span>](index.md)

[<span data-ttu-id="8ee5b-116">Eccezioni: funzione `raise`</span><span class="sxs-lookup"><span data-stu-id="8ee5b-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)

[<span data-ttu-id="8ee5b-117">Gerarchia delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="8ee5b-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
