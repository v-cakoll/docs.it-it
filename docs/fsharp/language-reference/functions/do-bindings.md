---
title: Associazioni do (F#)
description: "Informazioni su come un binding ' do' F # viene utilizzato per eseguire codice senza definire una funzione o un valore."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4c63da0c5e2f4130d59f9efa6bc54a55e5fe9fd8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="do-bindings"></a><span data-ttu-id="18a29-103">Associazioni do</span><span class="sxs-lookup"><span data-stu-id="18a29-103">do Bindings</span></span>

<span data-ttu-id="18a29-104">Oggetto `do` associazione viene utilizzata per eseguire codice senza definire una funzione o un valore.</span><span class="sxs-lookup"><span data-stu-id="18a29-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="18a29-105">Inoltre, eseguire i binding possono essere utilizzate nelle classi, vedere [ `do` associazioni nelle classi](../members/do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="18a29-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>


## <a name="syntax"></a><span data-ttu-id="18a29-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18a29-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="18a29-107">Note</span><span class="sxs-lookup"><span data-stu-id="18a29-107">Remarks</span></span>
<span data-ttu-id="18a29-108">Utilizzare un `do` associazione quando si desidera eseguire il codice in modo indipendente da una definizione di funzione o valore.</span><span class="sxs-lookup"><span data-stu-id="18a29-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="18a29-109">L'espressione in un `do` deve restituire l'associazione `unit`.</span><span class="sxs-lookup"><span data-stu-id="18a29-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="18a29-110">Codice in un livello superiore `do` associazione viene eseguita quando viene inizializzato il modulo.</span><span class="sxs-lookup"><span data-stu-id="18a29-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="18a29-111">La parola chiave `do` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="18a29-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="18a29-112">Gli attributi possono essere applicati a un livello superiore `do` associazione.</span><span class="sxs-lookup"><span data-stu-id="18a29-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="18a29-113">Ad esempio, se il programma utilizza l'interoperabilità COM, è possibile applicare il `STAThread` attributo al programma.</span><span class="sxs-lookup"><span data-stu-id="18a29-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="18a29-114">È possibile farlo con un attributo in un `do` binding, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="18a29-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a><span data-ttu-id="18a29-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18a29-115">See Also</span></span>
[<span data-ttu-id="18a29-116">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="18a29-116">F# Language Reference</span></span>](../index.md)

[<span data-ttu-id="18a29-117">Funzioni</span><span class="sxs-lookup"><span data-stu-id="18a29-117">Functions</span></span>](index.md)

