---
ms.openlocfilehash: 958a89015420ce5632d596688963d576c40b4cb6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235584"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="c9bba-101">Lo stato della sessione di condivisione con Asp.Net StateServer richiede che tutti i server nella Web farm usino la stessa versione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c9bba-101">Sharing session state with Asp.Net StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c9bba-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c9bba-102">Details</span></span>|<span data-ttu-id="c9bba-103">Quando si abilita lo stato della sessione <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=name>, tutti i server nella Web farm specificata devono usare la stessa versione di .NET Framework affinché lo stato venga condiviso correttamente.</span><span class="sxs-lookup"><span data-stu-id="c9bba-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=name> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>|
|<span data-ttu-id="c9bba-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="c9bba-104">Suggestion</span></span>|<span data-ttu-id="c9bba-105">Verificare di aggiornare le versioni di .NET Framework nei server Web che condividono lo stato nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="c9bba-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>|
|<span data-ttu-id="c9bba-106">Ambito</span><span class="sxs-lookup"><span data-stu-id="c9bba-106">Scope</span></span>|<span data-ttu-id="c9bba-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c9bba-107">Edge</span></span>|
|<span data-ttu-id="c9bba-108">Versione</span><span class="sxs-lookup"><span data-stu-id="c9bba-108">Version</span></span>|<span data-ttu-id="c9bba-109">4.5</span><span class="sxs-lookup"><span data-stu-id="c9bba-109">4.5</span></span>|
|<span data-ttu-id="c9bba-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="c9bba-110">Type</span></span>|<span data-ttu-id="c9bba-111">Runtime</span><span class="sxs-lookup"><span data-stu-id="c9bba-111">Runtime</span></span>|
|<span data-ttu-id="c9bba-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="c9bba-112">Affected APIs</span></span>|<ul><li><xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|
