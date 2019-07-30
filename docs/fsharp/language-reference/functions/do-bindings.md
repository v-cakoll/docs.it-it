---
title: Associazioni do
description: Informazioni sul modo F# in cui viene usata un'associazione ' do ' per eseguire il codice senza definire una funzione o un valore.
ms.date: 05/16/2016
ms.openlocfilehash: f98f523296bfaceeda35d4861eafbfeaa5a60c32
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630535"
---
# <a name="do-bindings"></a><span data-ttu-id="1ca54-103">Associazioni do</span><span class="sxs-lookup"><span data-stu-id="1ca54-103">do Bindings</span></span>

<span data-ttu-id="1ca54-104">Un' `do` associazione viene utilizzata per eseguire il codice senza definire una funzione o un valore.</span><span class="sxs-lookup"><span data-stu-id="1ca54-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="1ca54-105">Inoltre, le associazioni do possono essere utilizzate nelle classi, vedere [ `do` binding nelle classi](../members/do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="1ca54-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="1ca54-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ca54-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="1ca54-107">Note</span><span class="sxs-lookup"><span data-stu-id="1ca54-107">Remarks</span></span>

<span data-ttu-id="1ca54-108">Utilizzare un' `do` associazione quando si desidera eseguire il codice indipendentemente dalla definizione di una funzione o di un valore.</span><span class="sxs-lookup"><span data-stu-id="1ca54-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="1ca54-109">L'espressione in un' `do` associazione deve restituire `unit`.</span><span class="sxs-lookup"><span data-stu-id="1ca54-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="1ca54-110">Il codice in un'associazione di `do` primo livello viene eseguito quando il modulo viene inizializzato.</span><span class="sxs-lookup"><span data-stu-id="1ca54-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="1ca54-111">La parola `do` chiave è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1ca54-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="1ca54-112">Gli attributi possono essere applicati a un'associazione di `do` primo livello.</span><span class="sxs-lookup"><span data-stu-id="1ca54-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="1ca54-113">Se, ad esempio, il programma usa l'interoperabilità COM, potrebbe essere `STAThread` necessario applicare l'attributo al programma.</span><span class="sxs-lookup"><span data-stu-id="1ca54-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="1ca54-114">A tale scopo, è possibile utilizzare un attributo in `do` un'associazione, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="1ca54-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a><span data-ttu-id="1ca54-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ca54-115">See also</span></span>

- [<span data-ttu-id="1ca54-116">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="1ca54-116">F# Language Reference</span></span>](../index.md)
- [<span data-ttu-id="1ca54-117">Funzioni</span><span class="sxs-lookup"><span data-stu-id="1ca54-117">Functions</span></span>](index.md)
