---
title: Associazioni do (F#)
description: 'Informazioni su come un binding '' do'' F # viene utilizzato per eseguire codice senza definire una funzione o un valore.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4c1057a3-3aa1-4b64-b46a-25ffe33f0be9
ms.openlocfilehash: f2563d384b67c005c96c2ff487c786476d385e70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="do-bindings"></a><span data-ttu-id="ca5fe-104">Associazioni do</span><span class="sxs-lookup"><span data-stu-id="ca5fe-104">do Bindings</span></span>

<span data-ttu-id="ca5fe-105">Oggetto `do` associazione viene utilizzata per eseguire codice senza definire una funzione o un valore.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-105">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="ca5fe-106">Inoltre, eseguire i binding possono essere utilizzate nelle classi, vedere [ `do` associazioni nelle classi](../members/do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="ca5fe-106">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>


## <a name="syntax"></a><span data-ttu-id="ca5fe-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca5fe-107">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="ca5fe-108">Note</span><span class="sxs-lookup"><span data-stu-id="ca5fe-108">Remarks</span></span>
<span data-ttu-id="ca5fe-109">Utilizzare un `do` associazione quando si desidera eseguire il codice in modo indipendente da una definizione di funzione o valore.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-109">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="ca5fe-110">L'espressione in un `do` deve restituire l'associazione `unit`.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-110">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="ca5fe-111">Codice in un livello superiore `do` associazione viene eseguita quando viene inizializzato il modulo.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-111">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="ca5fe-112">La parola chiave `do` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-112">The keyword `do` is optional.</span></span>

<span data-ttu-id="ca5fe-113">Gli attributi possono essere applicati a un livello superiore `do` associazione.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-113">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="ca5fe-114">Ad esempio, se il programma utilizza l'interoperabilità COM, è possibile applicare il `STAThread` attributo al programma.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-114">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="ca5fe-115">È possibile farlo con un attributo in un `do` binding, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-115">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a><span data-ttu-id="ca5fe-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca5fe-116">See Also</span></span>
[<span data-ttu-id="ca5fe-117">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="ca5fe-117">F# Language Reference</span></span>](../index.md)

[<span data-ttu-id="ca5fe-118">Funzioni</span><span class="sxs-lookup"><span data-stu-id="ca5fe-118">Functions</span></span>](index.md)

