---
title: 'Mitigazione: Layout WPF'
description: Viene illustrato come attenuare i problemi derivanti da una modifica nel layout dei controlli WPF, ad esempio la posizione di un oggetto che si sposta di un pixel.
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
ms.openlocfilehash: e4e4612f7b39eefbf0e76ac86c8eb644c257ba75
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475346"
---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="2974d-103">Mitigazione: Layout WPF</span><span class="sxs-lookup"><span data-stu-id="2974d-103">Mitigation: WPF Layout</span></span>
<span data-ttu-id="2974d-104">Il layout dei controlli WPF può cambiare leggermente.</span><span class="sxs-lookup"><span data-stu-id="2974d-104">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="2974d-105">Impatto</span><span class="sxs-lookup"><span data-stu-id="2974d-105">Impact</span></span>  
 <span data-ttu-id="2974d-106">Come conseguenza di questo cambiamento:</span><span class="sxs-lookup"><span data-stu-id="2974d-106">As a result of this change:</span></span>  
  
- <span data-ttu-id="2974d-107">La larghezza o l'altezza degli elementi può aumentare o diminuire al massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="2974d-107">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
- <span data-ttu-id="2974d-108">La posizione di un oggetto può cambiare al massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="2974d-108">The placement of an object can move by at most one pixel.</span></span>  
  
- <span data-ttu-id="2974d-109">Gli elementi centrati possono risultare decentrati in orizzontale o in verticale al massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="2974d-109">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="2974d-110">Per impostazione predefinita, questo nuovo layout è disponibile solo per app destinate a .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="2974d-110">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="2974d-111">Strategia di riduzione del rischio</span><span class="sxs-lookup"><span data-stu-id="2974d-111">Mitigation</span></span>  
 <span data-ttu-id="2974d-112">Poiché questa modifica tende a eliminare il ritaglio del lato destro o inferiore dei controlli WPF a DPI elevati, le app destinate a versioni precedenti di .NET Framework ma eseguite su .NET Framework 4.6 possono adottare questo nuovo comportamento aggiungendo la riga seguente alla sezione `<runtime>` del file app.config:</span><span class="sxs-lookup"><span data-stu-id="2974d-112">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="2974d-113">Le app destinate a .NET Framework 4.6 ma che richiedono che il rendering dei controlli WPF venga eseguito mediante l'algoritmo di layout precedente possono aggiungere a questo scopo la riga seguente alla sezione `<runtime>` del file app.config:</span><span class="sxs-lookup"><span data-stu-id="2974d-113">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="2974d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2974d-114">See also</span></span>

- [<span data-ttu-id="2974d-115">Compatibilità tra le versioni</span><span class="sxs-lookup"><span data-stu-id="2974d-115">Application compatibility</span></span>](application-compatibility.md)
