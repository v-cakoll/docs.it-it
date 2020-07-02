---
ms.openlocfilehash: 0fe07ac21effacffc56d37ccb46a121f443acd20
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620176"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="f0219-101">Lo stato della sessione di condivisione con Asp.Net StateServer richiede che tutti i server nella Web farm usino la stessa versione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f0219-101">Sharing session state with Asp.Net StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="f0219-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f0219-102">Details</span></span>

<span data-ttu-id="f0219-103">Quando si abilita lo stato della sessione <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName>, tutti i server nella Web farm specificata devono usare la stessa versione di .NET Framework affinché lo stato venga condiviso correttamente.</span><span class="sxs-lookup"><span data-stu-id="f0219-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f0219-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="f0219-104">Suggestion</span></span>

<span data-ttu-id="f0219-105">Verificare di aggiornare le versioni di .NET Framework nei server Web che condividono lo stato nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="f0219-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>

| <span data-ttu-id="f0219-106">Nome</span><span class="sxs-lookup"><span data-stu-id="f0219-106">Name</span></span>    | <span data-ttu-id="f0219-107">Valore</span><span class="sxs-lookup"><span data-stu-id="f0219-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f0219-108">Scope</span><span class="sxs-lookup"><span data-stu-id="f0219-108">Scope</span></span>   |<span data-ttu-id="f0219-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f0219-109">Edge</span></span>|
|<span data-ttu-id="f0219-110">Version</span><span class="sxs-lookup"><span data-stu-id="f0219-110">Version</span></span>|<span data-ttu-id="f0219-111">4.5</span><span class="sxs-lookup"><span data-stu-id="f0219-111">4.5</span></span>|
|<span data-ttu-id="f0219-112">Type</span><span class="sxs-lookup"><span data-stu-id="f0219-112">Type</span></span>|<span data-ttu-id="f0219-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="f0219-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f0219-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="f0219-114">Affected APIs</span></span>

-<xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|
