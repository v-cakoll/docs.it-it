---
ms.openlocfilehash: af10716fe5f4c07091e8605cdf620e4a499fb1e8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620179"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a><span data-ttu-id="c591f-101">IPad non deve essere usato nel file di funzionalità personalizzato perché ora è una funzionalità del browser</span><span class="sxs-lookup"><span data-stu-id="c591f-101">IPad should not be used in custom capabilities file because it is now a browser capability</span></span>

#### <a name="details"></a><span data-ttu-id="c591f-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c591f-102">Details</span></span>

<span data-ttu-id="c591f-103">A partire da .NET Framework 4.5, iPad è un identificatore nel file di funzionalità del browser predefinito di ASP.NET, quindi non deve essere usato in un file di funzionalità personalizzato</span><span class="sxs-lookup"><span data-stu-id="c591f-103">Beginning in .NET Framework 4.5, iPad is an identifier in the default ASP.NET browser capabilities file, so it should not be used in a custom capabilities file</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c591f-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="c591f-104">Suggestion</span></span>

<span data-ttu-id="c591f-105">Se sono richieste funzionalità specifiche per iPad, è necessario modificare il comportamento di iPad impostando le funzionalità sul refID &quot;IPad&quot; predefinito del gateway anziché generando un nuovo ID &quot;IPad&quot; in base alla corrispondenza dell'agente utente.</span><span class="sxs-lookup"><span data-stu-id="c591f-105">If iPad-specific capabilities are required, it is necessary to modify iPad behavior by setting capabilities on the pre-defined gateway refID &quot;IPad&quot; instead of by generating a new &quot;IPad&quot; ID by user agent matching.</span></span>

| <span data-ttu-id="c591f-106">Nome</span><span class="sxs-lookup"><span data-stu-id="c591f-106">Name</span></span>    | <span data-ttu-id="c591f-107">Valore</span><span class="sxs-lookup"><span data-stu-id="c591f-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c591f-108">Scope</span><span class="sxs-lookup"><span data-stu-id="c591f-108">Scope</span></span>   |<span data-ttu-id="c591f-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c591f-109">Edge</span></span>|
|<span data-ttu-id="c591f-110">Version</span><span class="sxs-lookup"><span data-stu-id="c591f-110">Version</span></span>|<span data-ttu-id="c591f-111">4.5</span><span class="sxs-lookup"><span data-stu-id="c591f-111">4.5</span></span>|
|<span data-ttu-id="c591f-112">Type</span><span class="sxs-lookup"><span data-stu-id="c591f-112">Type</span></span>|<span data-ttu-id="c591f-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="c591f-113">Runtime</span></span>|
