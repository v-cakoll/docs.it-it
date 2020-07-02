---
ms.openlocfilehash: 4a65e721e5639f12445a9a44f46baa0d26898a88
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615674"
---
### <a name="il-ret-not-allowed-in-a-try-region"></a><span data-ttu-id="7b6e4-101">Istruzione IL ret non consentita in un'area try</span><span class="sxs-lookup"><span data-stu-id="7b6e4-101">IL ret not allowed in a try region</span></span>

#### <a name="details"></a><span data-ttu-id="7b6e4-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7b6e4-102">Details</span></span>

<span data-ttu-id="7b6e4-103">A differenza del compilatore JIT JIT64, RyuJIT (usato in .NET Framework 4.6) non consente un'istruzione IL ret in un'area try.</span><span class="sxs-lookup"><span data-stu-id="7b6e4-103">Unlike the JIT64 just-in-time compiler, RyuJIT (used in .NET Framework 4.6) does not allow an IL ret instruction in a try region.</span></span> <span data-ttu-id="7b6e4-104">La restituzione da un'area try non è consentita dalla specifica ECMA-335 e nessun compilatore gestito noto genera tale IL.</span><span class="sxs-lookup"><span data-stu-id="7b6e4-104">Returning from a try region is disallowed by the ECMA-335 specification, and no known managed compiler generates such IL.</span></span> <span data-ttu-id="7b6e4-105">Tuttavia, il compilatore JIT64 eseguirà tale livello di integrità se viene generato tramite reflection emit.</span><span class="sxs-lookup"><span data-stu-id="7b6e4-105">However, the JIT64 compiler will execute such IL if it is generated using reflection emit.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7b6e4-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="7b6e4-106">Suggestion</span></span>

<span data-ttu-id="7b6e4-107">Se un'app genera IL che include un codice operativo ret in un'area try, è possibile destinare l'app a .NET Framework 4.5 per usare il compilatore JIT precedente ed evitare l'interruzione.</span><span class="sxs-lookup"><span data-stu-id="7b6e4-107">If an app is generating IL that includes a ret opcode in a try region, the app may target .NET Framework 4.5 to use the old JIT and avoid this break.</span></span> <span data-ttu-id="7b6e4-108">In alternativa, l'IL generato può essere aggiornato per restituire il controllo dopo l'area try.</span><span class="sxs-lookup"><span data-stu-id="7b6e4-108">Alternatively, the generated IL may be updated to return after the try region.</span></span>

| <span data-ttu-id="7b6e4-109">Nome</span><span class="sxs-lookup"><span data-stu-id="7b6e4-109">Name</span></span>    | <span data-ttu-id="7b6e4-110">Valore</span><span class="sxs-lookup"><span data-stu-id="7b6e4-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7b6e4-111">Scope</span><span class="sxs-lookup"><span data-stu-id="7b6e4-111">Scope</span></span>   | <span data-ttu-id="7b6e4-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7b6e4-112">Edge</span></span>        |
| <span data-ttu-id="7b6e4-113">Version</span><span class="sxs-lookup"><span data-stu-id="7b6e4-113">Version</span></span> | <span data-ttu-id="7b6e4-114">4.6</span><span class="sxs-lookup"><span data-stu-id="7b6e4-114">4.6</span></span>         |
| <span data-ttu-id="7b6e4-115">Type</span><span class="sxs-lookup"><span data-stu-id="7b6e4-115">Type</span></span>    | <span data-ttu-id="7b6e4-116">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="7b6e4-116">Retargeting</span></span> |
