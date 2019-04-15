---
ms.openlocfilehash: ee5070a1a4c58d6c1282ba47c921436ca22722ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234258"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a><span data-ttu-id="bd5cd-101">.NET Framework 4.6 non usa una versione 4.5.x.x durante la registrazione nel Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="bd5cd-101">The .NET Framework 4.6 does not use a 4.5.x.x version when registering itself in the registry</span></span>

|   |   |
|---|---|
|<span data-ttu-id="bd5cd-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bd5cd-102">Details</span></span>|<span data-ttu-id="bd5cd-103">Come prevedibile, il set di chiavi della versione nel Registro di sistema (in <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) per .NET Framework 4.6 inizia con "4.6" e non "4.5".</span><span class="sxs-lookup"><span data-stu-id="bd5cd-103">As one might expect, the version key set in the registry (at <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) for the .NET Framework 4.6 begins with '4.6', not '4.5'.</span></span> <span data-ttu-id="bd5cd-104">Le app che dipendono da queste chiavi del Registro di sistema per conoscere le versioni di .NET Framework installate in un computer devono essere aggiornate in modo da comprendere che 4.6 è una nuova versione possibile che è compatibile con le precedenti versioni 4.5.x.</span><span class="sxs-lookup"><span data-stu-id="bd5cd-104">Apps that depend on these registry keys to know which .NET Framework versions are installed on a machine should be updated to understand that 4.6 is a new possible version, and one that is compatible with previous 4.5.x releases.</span></span>|
|<span data-ttu-id="bd5cd-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="bd5cd-105">Suggestion</span></span>|<span data-ttu-id="bd5cd-106">Aggiornare le app che sondano un'installazione di .NET Framework 4.5 cercando le chiavi del Registro di sistema 4.5 in modo che accettino anche la versione 4.6.</span><span class="sxs-lookup"><span data-stu-id="bd5cd-106">Update apps probing for a .NET Framework 4.5 install by looking for 4.5 registry keys to also accept 4.6.</span></span>|
|<span data-ttu-id="bd5cd-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="bd5cd-107">Scope</span></span>|<span data-ttu-id="bd5cd-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bd5cd-108">Edge</span></span>|
|<span data-ttu-id="bd5cd-109">Versione</span><span class="sxs-lookup"><span data-stu-id="bd5cd-109">Version</span></span>|<span data-ttu-id="bd5cd-110">4.6</span><span class="sxs-lookup"><span data-stu-id="bd5cd-110">4.6</span></span>|
|<span data-ttu-id="bd5cd-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="bd5cd-111">Type</span></span>|<span data-ttu-id="bd5cd-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="bd5cd-112">Runtime</span></span>|
