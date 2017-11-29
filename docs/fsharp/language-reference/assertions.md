---
title: Asserzioni (F#)
description: "Informazioni su come utilizzare l'espressione 'assert' come una funzionalità di debug per il test di espressioni in linguaggio di programmazione c#."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2badaad7-f086-47e7-99c1-91f35117da83
ms.openlocfilehash: 56891769602afaa765ebfe7e7822a179c7a22968
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="assertions"></a><span data-ttu-id="cc09b-104">Asserzioni</span><span class="sxs-lookup"><span data-stu-id="cc09b-104">Assertions</span></span>

<span data-ttu-id="cc09b-105">Il `assert` espressione è una funzionalità di debug che è possibile utilizzare per testare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="cc09b-105">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="cc09b-106">In caso di errore in modalità Debug, un'asserzione genera una finestra di dialogo di errore di sistema.</span><span class="sxs-lookup"><span data-stu-id="cc09b-106">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="cc09b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc09b-107">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="cc09b-108">Note</span><span class="sxs-lookup"><span data-stu-id="cc09b-108">Remarks</span></span>

<span data-ttu-id="cc09b-109">Il `assert` tipo dell'espressione è `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="cc09b-109">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="cc09b-110">Nella sintassi precedente, *condizione* rappresenta un'espressione booleana da testare.</span><span class="sxs-lookup"><span data-stu-id="cc09b-110">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="cc09b-111">Se l'espressione restituisce `true`, esecuzione continua.</span><span class="sxs-lookup"><span data-stu-id="cc09b-111">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="cc09b-112">Se restituisce `false`, viene generata una finestra di dialogo Errore di sistema.</span><span class="sxs-lookup"><span data-stu-id="cc09b-112">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="cc09b-113">La finestra di dialogo di errore ha una didascalia che contiene la stringa **asserzione non riuscita**.</span><span class="sxs-lookup"><span data-stu-id="cc09b-113">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="cc09b-114">Nella finestra di dialogo contiene una traccia dello stack che indica dove si è verificato l'errore di asserzione.</span><span class="sxs-lookup"><span data-stu-id="cc09b-114">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="cc09b-115">Il controllo delle asserzioni è abilitato solo quando si esegue la compilazione in modalità Debug. ovvero, se la costante `DEBUG` è definito.</span><span class="sxs-lookup"><span data-stu-id="cc09b-115">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="cc09b-116">Nel sistema del progetto, per impostazione predefinita, il `DEBUG` costante è definita nella configurazione di Debug, ma non nella configurazione di rilascio.</span><span class="sxs-lookup"><span data-stu-id="cc09b-116">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="cc09b-117">Errore di asserzione non può essere intercettato tramite la gestione delle eccezioni di F #.</span><span class="sxs-lookup"><span data-stu-id="cc09b-117">The assertion failure error cannot be caught by using F# exception handling.</span></span>

>[!NOTE]
<span data-ttu-id="cc09b-118">Il `assert` funzione si risolve in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cc09b-118">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="cc09b-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="cc09b-119">Example</span></span>

<span data-ttu-id="cc09b-120">Esempio di codice seguente viene illustrato l'utilizzo del `assert` espressione.</span><span class="sxs-lookup"><span data-stu-id="cc09b-120">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a><span data-ttu-id="cc09b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc09b-121">See Also</span></span>

[<span data-ttu-id="cc09b-122">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="cc09b-122">F# Language Reference</span></span>](index.md)
