---
title: Asserzioni
description: Informazioni su come usare l'espressione 'assert' come una funzionalità di debug per testare le espressioni in di F# linguaggio di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: c2d97386e87e9b915da490a78fff9aedb9def616
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61703218"
---
# <a name="assertions"></a><span data-ttu-id="87308-103">Asserzioni</span><span class="sxs-lookup"><span data-stu-id="87308-103">Assertions</span></span>

<span data-ttu-id="87308-104">Il `assert` espressione è una funzionalità di debug che è possibile usare per testare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="87308-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="87308-105">In caso di errore in modalità Debug, un'asserzione genera una finestra di dialogo di errore di sistema.</span><span class="sxs-lookup"><span data-stu-id="87308-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="87308-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87308-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="87308-107">Note</span><span class="sxs-lookup"><span data-stu-id="87308-107">Remarks</span></span>

<span data-ttu-id="87308-108">Il `assert` espressione con tipo `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="87308-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="87308-109">Nella sintassi precedente *condizione* rappresenta un'espressione booleana che deve essere testato.</span><span class="sxs-lookup"><span data-stu-id="87308-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="87308-110">Se l'espressione restituisce `true`, esecuzione continua senza interruzioni.</span><span class="sxs-lookup"><span data-stu-id="87308-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="87308-111">Se restituisce `false`, viene generata una finestra di dialogo di errore di sistema.</span><span class="sxs-lookup"><span data-stu-id="87308-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="87308-112">La finestra di dialogo di errore ha una didascalia che contiene la stringa **asserzione non riuscita**.</span><span class="sxs-lookup"><span data-stu-id="87308-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="87308-113">La finestra di dialogo contiene un'analisi dello stack che indica dove si è verificato l'errore di asserzione.</span><span class="sxs-lookup"><span data-stu-id="87308-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="87308-114">Il controllo delle asserzioni è abilitato solo quando si esegue la compilazione in modalità Debug. vale a dire, se la costante `DEBUG` è definito.</span><span class="sxs-lookup"><span data-stu-id="87308-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="87308-115">Nel sistema del progetto, per impostazione predefinita, il `DEBUG` costante è definita nella configurazione di Debug ma non nella configurazione di rilascio.</span><span class="sxs-lookup"><span data-stu-id="87308-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="87308-116">Errore di asserzione non può essere intercettato tramite F# gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="87308-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

> [!NOTE]
> <span data-ttu-id="87308-117">Il `assert` funzione si risolve in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="87308-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="87308-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="87308-118">Example</span></span>

<span data-ttu-id="87308-119">Esempio di codice seguente viene illustrato l'utilizzo del `assert` espressione.</span><span class="sxs-lookup"><span data-stu-id="87308-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="87308-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87308-120">See also</span></span>

- [<span data-ttu-id="87308-121">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="87308-121">F# Language Reference</span></span>](index.md)