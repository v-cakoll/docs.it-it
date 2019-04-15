---
ms.openlocfilehash: 84f570cbbd97be79426e117d4c97ec182a397fd4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235537"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a><span data-ttu-id="b1bb1-101">IPad non deve essere usato nel file di funzionalità personalizzato perché ora è una funzionalità del browser</span><span class="sxs-lookup"><span data-stu-id="b1bb1-101">IPad should not be used in custom capabilities file because it is now a browser capability</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b1bb1-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b1bb1-102">Details</span></span>|<span data-ttu-id="b1bb1-103">A partire da .NET Framework 4.5, iPad è un identificatore nel file di funzionalità del browser predefinito di ASP.NET, quindi non deve essere usato in un file di funzionalità personalizzato</span><span class="sxs-lookup"><span data-stu-id="b1bb1-103">Beginning in .NET Framework 4.5, iPad is an identifier in the default ASP.NET browser capabilities file, so it should not be used in a custom capabilities file</span></span>|
|<span data-ttu-id="b1bb1-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b1bb1-104">Suggestion</span></span>|<span data-ttu-id="b1bb1-105">Se sono richieste funzionalità specifiche per iPad, è necessario modificare il comportamento di iPad impostando le funzionalità sul refID &quot;IPad&quot; predefinito del gateway anziché generando un nuovo ID &quot;IPad&quot; in base alla corrispondenza dell'agente utente.</span><span class="sxs-lookup"><span data-stu-id="b1bb1-105">If iPad-specific capabilities are required, it is necessary to modify iPad behavior by setting capabilities on the pre-defined gateway refID &quot;IPad&quot; instead of by generating a new &quot;IPad&quot; ID by user agent matching.</span></span>|
|<span data-ttu-id="b1bb1-106">Ambito</span><span class="sxs-lookup"><span data-stu-id="b1bb1-106">Scope</span></span>|<span data-ttu-id="b1bb1-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b1bb1-107">Edge</span></span>|
|<span data-ttu-id="b1bb1-108">Versione</span><span class="sxs-lookup"><span data-stu-id="b1bb1-108">Version</span></span>|<span data-ttu-id="b1bb1-109">4.5</span><span class="sxs-lookup"><span data-stu-id="b1bb1-109">4.5</span></span>|
|<span data-ttu-id="b1bb1-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="b1bb1-110">Type</span></span>|<span data-ttu-id="b1bb1-111">Runtime</span><span class="sxs-lookup"><span data-stu-id="b1bb1-111">Runtime</span></span>|
