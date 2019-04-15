---
ms.openlocfilehash: 1687b1b9a1a6861f9569a0e29426de7f32ffc32b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234455"
---
### <a name="il-ret-not-allowed-in-a-try-region"></a><span data-ttu-id="d4875-101">Istruzione IL ret non consentita in un'area try</span><span class="sxs-lookup"><span data-stu-id="d4875-101">IL ret not allowed in a try region</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d4875-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d4875-102">Details</span></span>|<span data-ttu-id="d4875-103">A differenza del compilatore JIT JIT64, RyuJIT (usato in .NET Framework 4.6) non consente un'istruzione IL ret in un'area try.</span><span class="sxs-lookup"><span data-stu-id="d4875-103">Unlike the JIT64 just-in-time compiler, RyuJIT (used in .NET Framework 4.6) does not allow an IL ret instruction in a try region.</span></span> <span data-ttu-id="d4875-104">La restituzione da un'area try non è consentita dalla specifica ECMA-335 e nessun compilatore gestito noto genera tale IL.</span><span class="sxs-lookup"><span data-stu-id="d4875-104">Returning from a try region is disallowed by the ECMA-335 specification, and no known managed compiler generates such IL.</span></span> <span data-ttu-id="d4875-105">Tuttavia, il compilatore JIT64 eseguirà tale livello di integrità se viene generato tramite reflection emit.</span><span class="sxs-lookup"><span data-stu-id="d4875-105">However, the JIT64 compiler will execute such IL if it is generated using reflection emit.</span></span>|
|<span data-ttu-id="d4875-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d4875-106">Suggestion</span></span>|<span data-ttu-id="d4875-107">Se un'app genera IL che include un codice operativo ret in un'area try, è possibile destinare l'app a .NET Framework 4.5 per usare il compilatore JIT precedente ed evitare l'interruzione.</span><span class="sxs-lookup"><span data-stu-id="d4875-107">If an app is generating IL that includes a ret opcode in a try region, the app may target .NET Framework 4.5 to use the old JIT and avoid this break.</span></span> <span data-ttu-id="d4875-108">In alternativa, l'IL generato può essere aggiornato per restituire il controllo dopo l'area try.</span><span class="sxs-lookup"><span data-stu-id="d4875-108">Alternatively, the generated IL may be updated to return after the try region.</span></span>|
|<span data-ttu-id="d4875-109">Ambito</span><span class="sxs-lookup"><span data-stu-id="d4875-109">Scope</span></span>|<span data-ttu-id="d4875-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d4875-110">Edge</span></span>|
|<span data-ttu-id="d4875-111">Versione</span><span class="sxs-lookup"><span data-stu-id="d4875-111">Version</span></span>|<span data-ttu-id="d4875-112">4.6</span><span class="sxs-lookup"><span data-stu-id="d4875-112">4.6</span></span>|
|<span data-ttu-id="d4875-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="d4875-113">Type</span></span>|<span data-ttu-id="d4875-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="d4875-114">Retargeting</span></span>|
