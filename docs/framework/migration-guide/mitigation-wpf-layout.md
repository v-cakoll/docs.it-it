---
title: 'Mitigazione: Layout WPF'
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
ms.openlocfilehash: 3e08a2d11e815248d0fe73f804e9ef7edb7c04da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126104"
---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="e2aab-102">Mitigazione: Layout WPF</span><span class="sxs-lookup"><span data-stu-id="e2aab-102">Mitigation: WPF Layout</span></span>
<span data-ttu-id="e2aab-103">Il layout dei controlli WPF può cambiare leggermente.</span><span class="sxs-lookup"><span data-stu-id="e2aab-103">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="e2aab-104">Impatto</span><span class="sxs-lookup"><span data-stu-id="e2aab-104">Impact</span></span>  
 <span data-ttu-id="e2aab-105">Come conseguenza di questo cambiamento:</span><span class="sxs-lookup"><span data-stu-id="e2aab-105">As a result of this change:</span></span>  
  
- <span data-ttu-id="e2aab-106">La larghezza o l'altezza degli elementi può aumentare o diminuire al massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="e2aab-106">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
- <span data-ttu-id="e2aab-107">La posizione di un oggetto può cambiare al massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="e2aab-107">The placement of an object can move by at most one pixel.</span></span>  
  
- <span data-ttu-id="e2aab-108">Gli elementi centrati possono risultare decentrati in orizzontale o in verticale al massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="e2aab-108">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="e2aab-109">Per impostazione predefinita, questo nuovo layout è disponibile solo per app destinate a .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="e2aab-109">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="e2aab-110">Attenuazione</span><span class="sxs-lookup"><span data-stu-id="e2aab-110">Mitigation</span></span>  
 <span data-ttu-id="e2aab-111">Poiché questa modifica tende a eliminare il ritaglio del lato destro o inferiore dei controlli WPF a DPI elevati, le app destinate a versioni precedenti di .NET Framework ma eseguite su .NET Framework 4.6 possono adottare questo nuovo comportamento aggiungendo la riga seguente alla sezione `<runtime>` del file app.config:</span><span class="sxs-lookup"><span data-stu-id="e2aab-111">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="e2aab-112">Le app destinate a .NET Framework 4.6 ma che richiedono che il rendering dei controlli WPF venga eseguito mediante l'algoritmo di layout precedente possono aggiungere a questo scopo la riga seguente alla sezione `<runtime>` del file app.config:</span><span class="sxs-lookup"><span data-stu-id="e2aab-112">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2aab-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2aab-113">See also</span></span>

- [<span data-ttu-id="e2aab-114">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="e2aab-114">Retargeting Changes</span></span>](retargeting-changes-in-the-net-framework-4-6.md)
