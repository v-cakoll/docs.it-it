---
title: Asserzioni
description: Informazioni su come usare l'espressione "Assert" come funzionalità di debug per il F# test delle espressioni nel linguaggio di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: b8b7e9662143b432d650f87515d4af31cced4149
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630033"
---
# <a name="assertions"></a><span data-ttu-id="e1d4c-103">Asserzioni</span><span class="sxs-lookup"><span data-stu-id="e1d4c-103">Assertions</span></span>

<span data-ttu-id="e1d4c-104">L' `assert` espressione è una funzionalità di debug che è possibile utilizzare per testare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="e1d4c-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="e1d4c-105">In caso di errore in modalità Debug, un'asserzione genera una finestra di dialogo di errore di sistema.</span><span class="sxs-lookup"><span data-stu-id="e1d4c-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="e1d4c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1d4c-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="e1d4c-107">Note</span><span class="sxs-lookup"><span data-stu-id="e1d4c-107">Remarks</span></span>

<span data-ttu-id="e1d4c-108">L' `assert` espressione è di `bool -> unit`tipo.</span><span class="sxs-lookup"><span data-stu-id="e1d4c-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="e1d4c-109">Nella sintassi precedente, *Condition* rappresenta un'espressione booleana che deve essere testata.</span><span class="sxs-lookup"><span data-stu-id="e1d4c-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="e1d4c-110">Se l'espressione restituisce `true`, l'esecuzione continua senza effetti.</span><span class="sxs-lookup"><span data-stu-id="e1d4c-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="e1d4c-111">Se restituisce, viene generata `false`una finestra di dialogo di errore di sistema.</span><span class="sxs-lookup"><span data-stu-id="e1d4c-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="e1d4c-112">Nella finestra di dialogo di errore è presente una didascalia che contiene l'asserzione di stringa **non riuscita**.</span><span class="sxs-lookup"><span data-stu-id="e1d4c-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="e1d4c-113">La finestra di dialogo contiene una traccia dello stack che indica dove si è verificato l'errore di asserzione.</span><span class="sxs-lookup"><span data-stu-id="e1d4c-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="e1d4c-114">Il controllo dell'asserzione è abilitato solo quando si esegue la compilazione in modalità di debug; ovvero se la costante `DEBUG` è definita.</span><span class="sxs-lookup"><span data-stu-id="e1d4c-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="e1d4c-115">Nel sistema del progetto, per impostazione predefinita, `DEBUG` la costante è definita nella configurazione di debug, ma non nella configurazione di rilascio.</span><span class="sxs-lookup"><span data-stu-id="e1d4c-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="e1d4c-116">L'errore di asserzione non può essere rilevato F# tramite la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="e1d4c-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

> [!NOTE]
> <span data-ttu-id="e1d4c-117">La `assert` funzione viene risolta in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e1d4c-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="e1d4c-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1d4c-118">Example</span></span>

<span data-ttu-id="e1d4c-119">Nell'esempio di codice riportato di seguito viene illustrato l' `assert` utilizzo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="e1d4c-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="e1d4c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1d4c-120">See also</span></span>

- [<span data-ttu-id="e1d4c-121">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="e1d4c-121">F# Language Reference</span></span>](index.md)
