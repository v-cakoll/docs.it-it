---
ms.openlocfilehash: 907c4aa5573c392a68afad0a4d937eadcd556440
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620294"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="3e52d-101">I valori di unione Null non risultano visibili nel debugger fino al passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="3e52d-101">Null coalescer values are not visible in debugger until one step later</span></span>

#### <a name="details"></a><span data-ttu-id="3e52d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3e52d-102">Details</span></span>

<span data-ttu-id="3e52d-103">A causa di un bug in .NET Framework 4.5, i valori impostati tramite un'operazione di unione Null non sono visibili nel debugger immediatamente dopo l'esecuzione dell'operazione di assegnazione quando si usa la versione a 64 bit del framework.</span><span class="sxs-lookup"><span data-stu-id="3e52d-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3e52d-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="3e52d-104">Suggestion</span></span>

<span data-ttu-id="3e52d-105">L'esecuzione di un ulteriore passo nel debugger determinerà il corretto aggiornamento del valore locale o del valore del campo.</span><span class="sxs-lookup"><span data-stu-id="3e52d-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="3e52d-106">Questo problema è stato corretto in .NET Framework 4.6. L'aggiornamento a questa versione del framework dovrebbe quindi risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="3e52d-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>

| <span data-ttu-id="3e52d-107">Nome</span><span class="sxs-lookup"><span data-stu-id="3e52d-107">Name</span></span>    | <span data-ttu-id="3e52d-108">Valore</span><span class="sxs-lookup"><span data-stu-id="3e52d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3e52d-109">Scope</span><span class="sxs-lookup"><span data-stu-id="3e52d-109">Scope</span></span>   |<span data-ttu-id="3e52d-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3e52d-110">Edge</span></span>|
|<span data-ttu-id="3e52d-111">Version</span><span class="sxs-lookup"><span data-stu-id="3e52d-111">Version</span></span>|<span data-ttu-id="3e52d-112">4.5</span><span class="sxs-lookup"><span data-stu-id="3e52d-112">4.5</span></span>|
|<span data-ttu-id="3e52d-113">Type</span><span class="sxs-lookup"><span data-stu-id="3e52d-113">Type</span></span>|<span data-ttu-id="3e52d-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="3e52d-114">Runtime</span></span>|
