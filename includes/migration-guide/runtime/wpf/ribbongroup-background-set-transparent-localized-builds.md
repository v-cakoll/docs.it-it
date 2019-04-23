---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236049"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="d1bdd-101">Viene impostato lo sfondo trasparente per RibbonGroup nelle build localizzate</span><span class="sxs-lookup"><span data-stu-id="d1bdd-101">RibbonGroup background is set to transparent in localized builds</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d1bdd-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d1bdd-102">Details</span></span>|<xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> <span data-ttu-id="d1bdd-103">Lo sfondo di RibbonGroup nelle build localizzate viene sempre disegnato con il pennello trasparente, causando un'esperienza insoddisfacente per l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="d1bdd-103">background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="d1bdd-104">Questo problema è stato risolto nella correzione di WPF per .NET Framework 4.7 con l'aggiornamento delle risorse localizzate per <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, che a sua volta garantisce che sia selezionato il pennello corretto.</span><span class="sxs-lookup"><span data-stu-id="d1bdd-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, which in turn ensures that the correct brush is selected.</span></span>|
|<span data-ttu-id="d1bdd-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d1bdd-105">Suggestion</span></span>|<span data-ttu-id="d1bdd-106">Effettuare l'aggiornamento a .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="d1bdd-106">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="d1bdd-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="d1bdd-107">Scope</span></span>|<span data-ttu-id="d1bdd-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d1bdd-108">Edge</span></span>|
|<span data-ttu-id="d1bdd-109">Versione</span><span class="sxs-lookup"><span data-stu-id="d1bdd-109">Version</span></span>|<span data-ttu-id="d1bdd-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d1bdd-110">4.6.2</span></span>|
|<span data-ttu-id="d1bdd-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="d1bdd-111">Type</span></span>|<span data-ttu-id="d1bdd-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="d1bdd-112">Runtime</span></span>|
