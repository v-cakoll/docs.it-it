---
title: Asserzioni (F#)
description: "Informazioni su come usare l'espressione 'assert' come una funzionalità di debug per testare le espressioni nel linguaggio di programmazione F #."
ms.date: 05/16/2016
ms.openlocfilehash: 85b1e839bfd19bada48b7f1821d15ddd8fa77754
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44097538"
---
# <a name="assertions"></a><span data-ttu-id="f88d7-103">Asserzioni</span><span class="sxs-lookup"><span data-stu-id="f88d7-103">Assertions</span></span>

<span data-ttu-id="f88d7-104">Il `assert` espressione è una funzionalità di debug che è possibile usare per testare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="f88d7-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="f88d7-105">In caso di errore in modalità Debug, un'asserzione genera una finestra di dialogo di errore di sistema.</span><span class="sxs-lookup"><span data-stu-id="f88d7-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="f88d7-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f88d7-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="f88d7-107">Note</span><span class="sxs-lookup"><span data-stu-id="f88d7-107">Remarks</span></span>

<span data-ttu-id="f88d7-108">Il `assert` espressione con tipo `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="f88d7-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="f88d7-109">Nella sintassi precedente *condizione* rappresenta un'espressione booleana che deve essere testato.</span><span class="sxs-lookup"><span data-stu-id="f88d7-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="f88d7-110">Se l'espressione restituisce `true`, esecuzione continua senza interruzioni.</span><span class="sxs-lookup"><span data-stu-id="f88d7-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="f88d7-111">Se restituisce `false`, viene generata una finestra di dialogo di errore di sistema.</span><span class="sxs-lookup"><span data-stu-id="f88d7-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="f88d7-112">La finestra di dialogo di errore ha una didascalia che contiene la stringa **asserzione non riuscita**.</span><span class="sxs-lookup"><span data-stu-id="f88d7-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="f88d7-113">La finestra di dialogo contiene un'analisi dello stack che indica dove si è verificato l'errore di asserzione.</span><span class="sxs-lookup"><span data-stu-id="f88d7-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="f88d7-114">Il controllo delle asserzioni è abilitato solo quando si esegue la compilazione in modalità Debug. vale a dire, se la costante `DEBUG` è definito.</span><span class="sxs-lookup"><span data-stu-id="f88d7-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="f88d7-115">Nel sistema del progetto, per impostazione predefinita, il `DEBUG` costante è definita nella configurazione di Debug ma non nella configurazione di rilascio.</span><span class="sxs-lookup"><span data-stu-id="f88d7-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="f88d7-116">Errore di asserzione non può essere intercettato tramite la gestione delle eccezioni di F #.</span><span class="sxs-lookup"><span data-stu-id="f88d7-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

>[!NOTE]
<span data-ttu-id="f88d7-117">Il `assert` funzione si risolve in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f88d7-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="f88d7-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="f88d7-118">Example</span></span>

<span data-ttu-id="f88d7-119">Esempio di codice seguente viene illustrato l'utilizzo del `assert` espressione.</span><span class="sxs-lookup"><span data-stu-id="f88d7-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="f88d7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f88d7-120">See also</span></span>

- [<span data-ttu-id="f88d7-121">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="f88d7-121">F# Language Reference</span></span>](index.md)
