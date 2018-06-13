---
title: Asserzioni (F#)
description: Informazioni su come utilizzare l'espressione 'assert' come una funzionalità di debug per il test di espressioni in linguaggio di programmazione c#.
ms.date: 05/16/2016
ms.openlocfilehash: 83e6cd77bbbb2c32e9b778e5bf6dd9d2e9c8fe32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563146"
---
# <a name="assertions"></a><span data-ttu-id="3fcef-103">Asserzioni</span><span class="sxs-lookup"><span data-stu-id="3fcef-103">Assertions</span></span>

<span data-ttu-id="3fcef-104">Il `assert` espressione è una funzionalità di debug che è possibile utilizzare per testare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="3fcef-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="3fcef-105">In caso di errore in modalità Debug, un'asserzione genera una finestra di dialogo di errore di sistema.</span><span class="sxs-lookup"><span data-stu-id="3fcef-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="3fcef-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fcef-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="3fcef-107">Note</span><span class="sxs-lookup"><span data-stu-id="3fcef-107">Remarks</span></span>

<span data-ttu-id="3fcef-108">Il `assert` tipo dell'espressione è `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="3fcef-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="3fcef-109">Nella sintassi precedente, *condizione* rappresenta un'espressione booleana da testare.</span><span class="sxs-lookup"><span data-stu-id="3fcef-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="3fcef-110">Se l'espressione restituisce `true`, esecuzione continua.</span><span class="sxs-lookup"><span data-stu-id="3fcef-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="3fcef-111">Se restituisce `false`, viene generata una finestra di dialogo Errore di sistema.</span><span class="sxs-lookup"><span data-stu-id="3fcef-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="3fcef-112">La finestra di dialogo di errore ha una didascalia che contiene la stringa **asserzione non riuscita**.</span><span class="sxs-lookup"><span data-stu-id="3fcef-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="3fcef-113">Nella finestra di dialogo contiene una traccia dello stack che indica dove si è verificato l'errore di asserzione.</span><span class="sxs-lookup"><span data-stu-id="3fcef-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="3fcef-114">Il controllo delle asserzioni è abilitato solo quando si esegue la compilazione in modalità Debug. ovvero, se la costante `DEBUG` è definito.</span><span class="sxs-lookup"><span data-stu-id="3fcef-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="3fcef-115">Nel sistema del progetto, per impostazione predefinita, il `DEBUG` costante è definita nella configurazione di Debug, ma non nella configurazione di rilascio.</span><span class="sxs-lookup"><span data-stu-id="3fcef-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="3fcef-116">Errore di asserzione non può essere intercettato tramite la gestione delle eccezioni di F #.</span><span class="sxs-lookup"><span data-stu-id="3fcef-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

>[!NOTE]
<span data-ttu-id="3fcef-117">Il `assert` funzione si risolve in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3fcef-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="3fcef-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="3fcef-118">Example</span></span>

<span data-ttu-id="3fcef-119">Esempio di codice seguente viene illustrato l'utilizzo del `assert` espressione.</span><span class="sxs-lookup"><span data-stu-id="3fcef-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a><span data-ttu-id="3fcef-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fcef-120">See Also</span></span>

[<span data-ttu-id="3fcef-121">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="3fcef-121">F# Language Reference</span></span>](index.md)
