---
ms.openlocfilehash: a3ba42868577ac20ea2e082f90fc4973a1bfe108
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622362"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="9839f-101">Viene impostato lo sfondo trasparente per RibbonGroup nelle build localizzate</span><span class="sxs-lookup"><span data-stu-id="9839f-101">RibbonGroup background is set to transparent in localized builds</span></span>

#### <a name="details"></a><span data-ttu-id="9839f-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9839f-102">Details</span></span>

<span data-ttu-id="9839f-103">Lo sfondo di <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> nelle build localizzate viene sempre disegnato con il pennello trasparente, causando un'esperienza insoddisfacente per l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="9839f-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="9839f-104">Questo problema è stato risolto nella correzione di WPF per .NET Framework 4.7 con l'aggiornamento delle risorse localizzate per <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, che a sua volta garantisce che sia selezionato il pennello corretto.</span><span class="sxs-lookup"><span data-stu-id="9839f-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, which in turn ensures that the correct brush is selected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9839f-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="9839f-105">Suggestion</span></span>

<span data-ttu-id="9839f-106">Effettuare l'aggiornamento a .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="9839f-106">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="9839f-107">Nome</span><span class="sxs-lookup"><span data-stu-id="9839f-107">Name</span></span>    | <span data-ttu-id="9839f-108">Valore</span><span class="sxs-lookup"><span data-stu-id="9839f-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9839f-109">Scope</span><span class="sxs-lookup"><span data-stu-id="9839f-109">Scope</span></span>   |<span data-ttu-id="9839f-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9839f-110">Edge</span></span>|
|<span data-ttu-id="9839f-111">Version</span><span class="sxs-lookup"><span data-stu-id="9839f-111">Version</span></span>|<span data-ttu-id="9839f-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="9839f-112">4.6.2</span></span>|
|<span data-ttu-id="9839f-113">Type</span><span class="sxs-lookup"><span data-stu-id="9839f-113">Type</span></span>|<span data-ttu-id="9839f-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="9839f-114">Runtime</span></span>|
