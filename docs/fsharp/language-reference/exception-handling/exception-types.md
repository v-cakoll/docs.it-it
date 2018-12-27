---
title: Tipi di eccezione
description: Informazioni su come definire e usare F# tipi di eccezione.
ms.date: 05/16/2016
ms.openlocfilehash: ed721dd0dc46a486fafeac2fa4c096800995ccb7
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612829"
---
# <a name="exception-types"></a><span data-ttu-id="2fc6c-103">Tipi di eccezione</span><span class="sxs-lookup"><span data-stu-id="2fc6c-103">Exception Types</span></span>

<span data-ttu-id="2fc6c-104">Esistono due categorie di eccezioni in F#: i tipi di eccezione .NET e F# tipi di eccezione.</span><span class="sxs-lookup"><span data-stu-id="2fc6c-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="2fc6c-105">Questo argomento descrive come definire e usare F# tipi di eccezione.</span><span class="sxs-lookup"><span data-stu-id="2fc6c-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="2fc6c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2fc6c-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="2fc6c-107">Note</span><span class="sxs-lookup"><span data-stu-id="2fc6c-107">Remarks</span></span>

<span data-ttu-id="2fc6c-108">Nella sintassi precedente *-tipo di eccezione* è il nome di un nuovo F# tipo di eccezione, e *tipi di argomento* rappresenta il tipo di argomento che può essere fornito quando si genera un'eccezione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="2fc6c-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="2fc6c-109">È possibile specificare più argomenti usando un tipo di tupla per *tipi di argomento*.</span><span class="sxs-lookup"><span data-stu-id="2fc6c-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="2fc6c-110">Una tipica definizione per un F# eccezione è simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="2fc6c-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="2fc6c-111">È possibile generare un'eccezione di questo tipo usando il `raise` funzionare, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="2fc6c-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="2fc6c-112">È possibile usare un F# tipo di eccezione direttamente nei filtri in un `try...with` espressione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2fc6c-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="2fc6c-113">Il tipo di eccezione definito tramite il `exception` parola chiave in F# è un nuovo tipo che eredita da `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="2fc6c-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2fc6c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fc6c-114">See also</span></span>

- [<span data-ttu-id="2fc6c-115">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="2fc6c-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="2fc6c-116">Eccezioni: funzione `raise`</span><span class="sxs-lookup"><span data-stu-id="2fc6c-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="2fc6c-117">Gerarchia delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="2fc6c-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)