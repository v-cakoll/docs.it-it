---
ms.openlocfilehash: 150b98255b3075a8fe8cad60ce234206b788a5f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617187"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a><span data-ttu-id="c7583-101">Modifica della spaziatura nel controllo TextBox ASP.Net multiriga quando si usa AntiXSSEncoder</span><span class="sxs-lookup"><span data-stu-id="c7583-101">Multi-line ASP.Net TextBox spacing changed when using AntiXSSEncoder</span></span>

#### <a name="details"></a><span data-ttu-id="c7583-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c7583-102">Details</span></span>

<span data-ttu-id="c7583-103">In .NET Framework 4.0 vengono inserite righe aggiuntive tra le righe di una casella di testo a più righe durante il postback, se si usa <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="c7583-103">In .NET Framework 4.0, extra lines were inserted between lines of a multi-line text box on postback, if using the <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>.</span></span> <span data-ttu-id="c7583-104">In .NET Framework 4.5 queste interruzioni di riga aggiuntive non vengono incluse, ma solo se l'app Web è destinata a .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="c7583-104">In .NET Framework 4.5, those extra line breaks are not included, but only if the web app is targeting .NET Framework 4.5</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c7583-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="c7583-105">Suggestion</span></span>

<span data-ttu-id="c7583-106">Tenere presente che le app Web 4.0 ridestinate a .NET Framework 4.5, possono avere caselle di testo a più righe migliorate in modo che non vengano più inserite interruzioni di riga aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="c7583-106">Be aware that 4.0 web apps retargeted to .NET Framework 4.5 may have multi-line text boxes improved to no longer insert extra line breaks.</span></span> <span data-ttu-id="c7583-107">Se non è opportuno, l'app può avere il comportamento precedente quando viene eseguita in .NET Framework 4.5 usando .NET Framework 4.0 come destinazione.</span><span class="sxs-lookup"><span data-stu-id="c7583-107">If this is not desirable, the app  can have the old behavior when running on .NET Framework 4.5 by targeting the .NET Framework 4.0.</span></span>

| <span data-ttu-id="c7583-108">Nome</span><span class="sxs-lookup"><span data-stu-id="c7583-108">Name</span></span>    | <span data-ttu-id="c7583-109">Valore</span><span class="sxs-lookup"><span data-stu-id="c7583-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c7583-110">Scope</span><span class="sxs-lookup"><span data-stu-id="c7583-110">Scope</span></span>   | <span data-ttu-id="c7583-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="c7583-111">Minor</span></span>       |
| <span data-ttu-id="c7583-112">Version</span><span class="sxs-lookup"><span data-stu-id="c7583-112">Version</span></span> | <span data-ttu-id="c7583-113">4.5</span><span class="sxs-lookup"><span data-stu-id="c7583-113">4.5</span></span>         |
| <span data-ttu-id="c7583-114">Type</span><span class="sxs-lookup"><span data-stu-id="c7583-114">Type</span></span>    | <span data-ttu-id="c7583-115">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="c7583-115">Retargeting</span></span> |
