---
title: Asserzioni
description: Informazioni su come usare l'espressione "Assert" come funzionalità di debug per il F# test delle espressioni nel linguaggio di programmazione.
ms.date: 10/22/2019
ms.openlocfilehash: 430db20e5ca307ba43a72e678a0424e03b0ac381
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799070"
---
# <a name="assertions"></a><span data-ttu-id="4613a-103">Asserzioni</span><span class="sxs-lookup"><span data-stu-id="4613a-103">Assertions</span></span>

<span data-ttu-id="4613a-104">L'espressione `assert` è una funzionalità di debug che è possibile utilizzare per testare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="4613a-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="4613a-105">In caso di errore in modalità Debug, un'asserzione genera una finestra di dialogo di errore di sistema.</span><span class="sxs-lookup"><span data-stu-id="4613a-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="4613a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4613a-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="4613a-107">Note</span><span class="sxs-lookup"><span data-stu-id="4613a-107">Remarks</span></span>

<span data-ttu-id="4613a-108">Il tipo dell'espressione `assert` è `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="4613a-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="4613a-109">La funzione `assert` viene risolta <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4613a-109">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4613a-110">Questo significa che il comportamento è identico a chiamare direttamente <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4613a-110">This means its behavior is identical to having called <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> directly.</span></span>

<span data-ttu-id="4613a-111">Il controllo dell'asserzione è abilitato solo quando si esegue la compilazione in modalità di debug; ovvero se viene definita la costante `DEBUG`.</span><span class="sxs-lookup"><span data-stu-id="4613a-111">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="4613a-112">Nel sistema del progetto, per impostazione predefinita, la costante `DEBUG` è definita nella configurazione di debug, ma non nella configurazione di rilascio.</span><span class="sxs-lookup"><span data-stu-id="4613a-112">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="4613a-113">L'errore di asserzione non può essere rilevato F# tramite la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="4613a-113">The assertion failure error cannot be caught by using F# exception handling.</span></span>

## <a name="example"></a><span data-ttu-id="4613a-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="4613a-114">Example</span></span>

<span data-ttu-id="4613a-115">Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo dell'espressione `assert`.</span><span class="sxs-lookup"><span data-stu-id="4613a-115">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="4613a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4613a-116">See also</span></span>

- [<span data-ttu-id="4613a-117">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="4613a-117">F# Language Reference</span></span>](index.md)
