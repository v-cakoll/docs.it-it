---
ms.openlocfilehash: ee5070a1a4c58d6c1282ba47c921436ca22722ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858632"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a><span data-ttu-id="fc285-101">.NET Framework 4.6 non usa una versione 4.5.x.x durante la registrazione nel Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="fc285-101">The .NET Framework 4.6 does not use a 4.5.x.x version when registering itself in the registry</span></span>

|   |   |
|---|---|
|<span data-ttu-id="fc285-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="fc285-102">Details</span></span>|<span data-ttu-id="fc285-103">Come prevedibile, il set di chiavi della versione nel Registro di sistema (in <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) per .NET Framework 4.6 inizia con "4.6" e non "4.5".</span><span class="sxs-lookup"><span data-stu-id="fc285-103">As one might expect, the version key set in the registry (at <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) for the .NET Framework 4.6 begins with '4.6', not '4.5'.</span></span> <span data-ttu-id="fc285-104">Le app che dipendono da queste chiavi del Registro di sistema per conoscere le versioni di .NET Framework installate in un computer devono essere aggiornate in modo da comprendere che 4.6 è una nuova versione possibile che è compatibile con le precedenti versioni 4.5.x.</span><span class="sxs-lookup"><span data-stu-id="fc285-104">Apps that depend on these registry keys to know which .NET Framework versions are installed on a machine should be updated to understand that 4.6 is a new possible version, and one that is compatible with previous 4.5.x releases.</span></span>|
|<span data-ttu-id="fc285-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="fc285-105">Suggestion</span></span>|<span data-ttu-id="fc285-106">Aggiornare le app che sondano un'installazione di .NET Framework 4.5 cercando le chiavi del Registro di sistema 4.5 in modo che accettino anche la versione 4.6.</span><span class="sxs-lookup"><span data-stu-id="fc285-106">Update apps probing for a .NET Framework 4.5 install by looking for 4.5 registry keys to also accept 4.6.</span></span>|
|<span data-ttu-id="fc285-107">Scope</span><span class="sxs-lookup"><span data-stu-id="fc285-107">Scope</span></span>|<span data-ttu-id="fc285-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="fc285-108">Edge</span></span>|
|<span data-ttu-id="fc285-109">Versione</span><span class="sxs-lookup"><span data-stu-id="fc285-109">Version</span></span>|<span data-ttu-id="fc285-110">4.6</span><span class="sxs-lookup"><span data-stu-id="fc285-110">4.6</span></span>|
|<span data-ttu-id="fc285-111">Type</span><span class="sxs-lookup"><span data-stu-id="fc285-111">Type</span></span>|<span data-ttu-id="fc285-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="fc285-112">Runtime</span></span>|
