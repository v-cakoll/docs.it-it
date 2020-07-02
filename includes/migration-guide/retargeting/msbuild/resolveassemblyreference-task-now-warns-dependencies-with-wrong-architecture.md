---
ms.openlocfilehash: 4d410811095786b33580d25f6c6eab3ac2f27148
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616105"
---
### <a name="resolveassemblyreference-task-now-warns-of-dependencies-with-the-wrong-architecture"></a><span data-ttu-id="aa11d-101">L'attiva ResolveAssemblyReference genera ora avvisi in caso di dipendenze con l'architettura non corretta</span><span class="sxs-lookup"><span data-stu-id="aa11d-101">ResolveAssemblyReference task now warns of dependencies with the wrong architecture</span></span>

#### <a name="details"></a><span data-ttu-id="aa11d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="aa11d-102">Details</span></span>

<span data-ttu-id="aa11d-103">L'attività genera un avviso, MSB3270, che indica la mancata corrispondenza di un riferimento o di una delle sue dipendenze all'architettura dell'app.</span><span class="sxs-lookup"><span data-stu-id="aa11d-103">The task emits a warning, MSB3270, which indicates that a reference or any of its dependencies does not match the app's architecture.</span></span> <span data-ttu-id="aa11d-104">Questa situazione si verifica ad esempio se un'app compilata con l'opzione `AnyCPU` include un riferimento x86.</span><span class="sxs-lookup"><span data-stu-id="aa11d-104">For example, this occurs if an app that was compiled with the `AnyCPU` option includes an x86 reference.</span></span> <span data-ttu-id="aa11d-105">Uno scenario di questo tipo potrebbe provocare un errore dell'app in fase di esecuzione (nel caso descritto, se l'app viene distribuita come processo x64).</span><span class="sxs-lookup"><span data-stu-id="aa11d-105">Such a scenario could result in an app failure at run time (in this case, if the app is deployed as an x64 process).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="aa11d-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="aa11d-106">Suggestion</span></span>

<span data-ttu-id="aa11d-107">Le possibili conseguenze riguardano le aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa11d-107">There are two areas of impact:</span></span>

- <span data-ttu-id="aa11d-108">La ricompilazione genera avvisi che non venivano visualizzati quando l'app veniva compilata con una versione precedente di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="aa11d-108">Recompilation generates warnings that did not appear when the app was compiled under a previous version of MSBuild.</span></span> <span data-ttu-id="aa11d-109">Tuttavia, dal momento che l'avviso identifica una possibile fonte di errore di runtime, deve essere analizzato e affrontato.</span><span class="sxs-lookup"><span data-stu-id="aa11d-109">However, because the warning identifies a possible source of runtime failure, it should be investigated and addressed.</span></span>
- <span data-ttu-id="aa11d-110">Se gli avvisi vengono considerati errori, la compilazione dell'app non verrà completata.</span><span class="sxs-lookup"><span data-stu-id="aa11d-110">If warnings are treated as errors, the app will fail to compile.</span></span>

| <span data-ttu-id="aa11d-111">Nome</span><span class="sxs-lookup"><span data-stu-id="aa11d-111">Name</span></span>    | <span data-ttu-id="aa11d-112">Valore</span><span class="sxs-lookup"><span data-stu-id="aa11d-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="aa11d-113">Scope</span><span class="sxs-lookup"><span data-stu-id="aa11d-113">Scope</span></span>   | <span data-ttu-id="aa11d-114">Minorenne</span><span class="sxs-lookup"><span data-stu-id="aa11d-114">Minor</span></span>       |
| <span data-ttu-id="aa11d-115">Version</span><span class="sxs-lookup"><span data-stu-id="aa11d-115">Version</span></span> | <span data-ttu-id="aa11d-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="aa11d-116">4.5.1</span></span>       |
| <span data-ttu-id="aa11d-117">Type</span><span class="sxs-lookup"><span data-stu-id="aa11d-117">Type</span></span>    | <span data-ttu-id="aa11d-118">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="aa11d-118">Retargeting</span></span> |
