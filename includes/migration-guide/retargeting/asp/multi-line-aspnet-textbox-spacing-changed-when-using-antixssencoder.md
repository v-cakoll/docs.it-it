---
ms.openlocfilehash: e2bca42daebd25667ab2f312d5e59089b986503c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234691"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a><span data-ttu-id="f114e-101">Modifica della spaziatura nel controllo TextBox ASP.Net multiriga quando si usa AntiXSSEncoder</span><span class="sxs-lookup"><span data-stu-id="f114e-101">Multi-line ASP.Net TextBox spacing changed when using AntiXSSEncoder</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f114e-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f114e-102">Details</span></span>|<span data-ttu-id="f114e-103">In .NET Framework 4.0 vengono inserite righe aggiuntive tra le righe di una casella di testo a più righe durante il postback, se si usa <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="f114e-103">In .NET Framework 4.0, extra lines were inserted between lines of a multi-line text box on postback, if using the <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name>.</span></span> <span data-ttu-id="f114e-104">In .NET Framework 4.5 queste interruzioni di riga aggiuntive non vengono incluse, ma solo se l'app Web è destinata a .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="f114e-104">In .NET Framework 4.5, those extra line breaks are not included, but only if the web app is targeting .NET Framework 4.5</span></span>|
|<span data-ttu-id="f114e-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="f114e-105">Suggestion</span></span>|<span data-ttu-id="f114e-106">Tenere presente che le app Web 4.0 ridestinate a .NET Framework 4.5, possono avere caselle di testo a più righe migliorate in modo che non vengano più inserite interruzioni di riga aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="f114e-106">Be aware that 4.0 web apps retargeted to .NET Framework 4.5 may have multi-line text boxes improved to no longer insert extra line breaks.</span></span> <span data-ttu-id="f114e-107">Se non è opportuno, l'app può avere il comportamento precedente quando viene eseguita in .NET Framework 4.5 usando .NET Framework 4.0 come destinazione.</span><span class="sxs-lookup"><span data-stu-id="f114e-107">If this is not desirable, the app  can have the old behavior when running on .NET Framework 4.5 by targeting the .NET Framework 4.0.</span></span>|
|<span data-ttu-id="f114e-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="f114e-108">Scope</span></span>|<span data-ttu-id="f114e-109">Secondario</span><span class="sxs-lookup"><span data-stu-id="f114e-109">Minor</span></span>|
|<span data-ttu-id="f114e-110">Versione</span><span class="sxs-lookup"><span data-stu-id="f114e-110">Version</span></span>|<span data-ttu-id="f114e-111">4.5</span><span class="sxs-lookup"><span data-stu-id="f114e-111">4.5</span></span>|
|<span data-ttu-id="f114e-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="f114e-112">Type</span></span>|<span data-ttu-id="f114e-113">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="f114e-113">Retargeting</span></span>|
