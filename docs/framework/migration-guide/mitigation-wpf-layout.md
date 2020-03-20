---
title: 'Mitigazione: Layout WPF'
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
ms.openlocfilehash: 7a074698fd203d0c5f9b799bfee8a6a9cb40800e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457778"
---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="ae8df-102">Mitigazione: Layout WPF</span><span class="sxs-lookup"><span data-stu-id="ae8df-102">Mitigation: WPF Layout</span></span>
<span data-ttu-id="ae8df-103">Il layout dei controlli WPF può cambiare leggermente.</span><span class="sxs-lookup"><span data-stu-id="ae8df-103">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="ae8df-104">Impatto</span><span class="sxs-lookup"><span data-stu-id="ae8df-104">Impact</span></span>  
 <span data-ttu-id="ae8df-105">Come conseguenza di questo cambiamento:</span><span class="sxs-lookup"><span data-stu-id="ae8df-105">As a result of this change:</span></span>  
  
- <span data-ttu-id="ae8df-106">La larghezza o l'altezza degli elementi può aumentare o diminuire al massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="ae8df-106">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
- <span data-ttu-id="ae8df-107">La posizione di un oggetto può cambiare al massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="ae8df-107">The placement of an object can move by at most one pixel.</span></span>  
  
- <span data-ttu-id="ae8df-108">Gli elementi centrati possono risultare decentrati in orizzontale o in verticale al massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="ae8df-108">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="ae8df-109">Per impostazione predefinita, questo nuovo layout è disponibile solo per app destinate a .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="ae8df-109">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="ae8df-110">Strategia di riduzione del rischio</span><span class="sxs-lookup"><span data-stu-id="ae8df-110">Mitigation</span></span>  
 <span data-ttu-id="ae8df-111">Poiché questa modifica tende a eliminare il ritaglio del lato destro o inferiore dei controlli WPF a DPI elevati, le app destinate a versioni precedenti di .NET Framework ma eseguite su .NET Framework 4.6 possono adottare questo nuovo comportamento aggiungendo la riga seguente alla sezione `<runtime>` del file app.config:</span><span class="sxs-lookup"><span data-stu-id="ae8df-111">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="ae8df-112">Le app destinate a .NET Framework 4.6 ma che richiedono che il rendering dei controlli WPF venga eseguito mediante l'algoritmo di layout precedente possono aggiungere a questo scopo la riga seguente alla sezione `<runtime>` del file app.config:</span><span class="sxs-lookup"><span data-stu-id="ae8df-112">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae8df-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae8df-113">See also</span></span>

- [<span data-ttu-id="ae8df-114">Compatibilità tra le versioni</span><span class="sxs-lookup"><span data-stu-id="ae8df-114">Application compatibility</span></span>](application-compatibility.md)
