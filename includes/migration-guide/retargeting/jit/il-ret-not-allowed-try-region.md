---
ms.openlocfilehash: 1687b1b9a1a6861f9569a0e29426de7f32ffc32b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804411"
---
### <a name="il-ret-not-allowed-in-a-try-region"></a><span data-ttu-id="786b0-101">Istruzione IL ret non consentita in un'area try</span><span class="sxs-lookup"><span data-stu-id="786b0-101">IL ret not allowed in a try region</span></span>

|   |   |
|---|---|
|<span data-ttu-id="786b0-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="786b0-102">Details</span></span>|<span data-ttu-id="786b0-103">A differenza del compilatore JIT JIT64, RyuJIT (usato in .NET Framework 4.6) non consente un'istruzione IL ret in un'area try.</span><span class="sxs-lookup"><span data-stu-id="786b0-103">Unlike the JIT64 just-in-time compiler, RyuJIT (used in .NET Framework 4.6) does not allow an IL ret instruction in a try region.</span></span> <span data-ttu-id="786b0-104">La restituzione da un'area try non è consentita dalla specifica ECMA-335 e nessun compilatore gestito noto genera tale IL.</span><span class="sxs-lookup"><span data-stu-id="786b0-104">Returning from a try region is disallowed by the ECMA-335 specification, and no known managed compiler generates such IL.</span></span> <span data-ttu-id="786b0-105">Tuttavia, il compilatore JIT64 eseguirà tale livello di integrità se viene generato tramite reflection emit.</span><span class="sxs-lookup"><span data-stu-id="786b0-105">However, the JIT64 compiler will execute such IL if it is generated using reflection emit.</span></span>|
|<span data-ttu-id="786b0-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="786b0-106">Suggestion</span></span>|<span data-ttu-id="786b0-107">Se un'app genera IL che include un codice operativo ret in un'area try, è possibile destinare l'app a .NET Framework 4.5 per usare il compilatore JIT precedente ed evitare l'interruzione.</span><span class="sxs-lookup"><span data-stu-id="786b0-107">If an app is generating IL that includes a ret opcode in a try region, the app may target .NET Framework 4.5 to use the old JIT and avoid this break.</span></span> <span data-ttu-id="786b0-108">In alternativa, l'IL generato può essere aggiornato per restituire il controllo dopo l'area try.</span><span class="sxs-lookup"><span data-stu-id="786b0-108">Alternatively, the generated IL may be updated to return after the try region.</span></span>|
|<span data-ttu-id="786b0-109">Scope</span><span class="sxs-lookup"><span data-stu-id="786b0-109">Scope</span></span>|<span data-ttu-id="786b0-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="786b0-110">Edge</span></span>|
|<span data-ttu-id="786b0-111">Versione</span><span class="sxs-lookup"><span data-stu-id="786b0-111">Version</span></span>|<span data-ttu-id="786b0-112">4.6</span><span class="sxs-lookup"><span data-stu-id="786b0-112">4.6</span></span>|
|<span data-ttu-id="786b0-113">Type</span><span class="sxs-lookup"><span data-stu-id="786b0-113">Type</span></span>|<span data-ttu-id="786b0-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="786b0-114">Retargeting</span></span>|
