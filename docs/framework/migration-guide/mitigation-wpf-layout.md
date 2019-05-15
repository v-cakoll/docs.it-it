---
title: 'Mitigazione: Layout WPF'
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c261a025548b2d22f6df3051dbcdb637723d4324
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64599463"
---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="edf79-102">Mitigazione: Layout WPF</span><span class="sxs-lookup"><span data-stu-id="edf79-102">Mitigation: WPF Layout</span></span>
<span data-ttu-id="edf79-103">Il layout dei controlli WPF può cambiare leggermente.</span><span class="sxs-lookup"><span data-stu-id="edf79-103">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="edf79-104">Impatto</span><span class="sxs-lookup"><span data-stu-id="edf79-104">Impact</span></span>  
 <span data-ttu-id="edf79-105">Come conseguenza di questo cambiamento:</span><span class="sxs-lookup"><span data-stu-id="edf79-105">As a result of this change:</span></span>  
  
- <span data-ttu-id="edf79-106">La larghezza o l'altezza degli elementi può aumentare o diminuire al massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="edf79-106">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
- <span data-ttu-id="edf79-107">La posizione di un oggetto può cambiare al massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="edf79-107">The placement of an object can move by at most one pixel.</span></span>  
  
- <span data-ttu-id="edf79-108">Gli elementi centrati possono risultare decentrati in orizzontale o in verticale al massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="edf79-108">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="edf79-109">Per impostazione predefinita, questo nuovo layout è disponibile solo per app destinate a .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="edf79-109">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="edf79-110">Mitigazione</span><span class="sxs-lookup"><span data-stu-id="edf79-110">Mitigation</span></span>  
 <span data-ttu-id="edf79-111">Poiché questa modifica tende a eliminare il ritaglio del lato destro o inferiore dei controlli WPF a DPI elevati, le app destinate a versioni precedenti di .NET Framework ma eseguite su .NET Framework 4.6 possono adottare questo nuovo comportamento aggiungendo la riga seguente alla sezione `<runtime>` del file app.config:</span><span class="sxs-lookup"><span data-stu-id="edf79-111">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="edf79-112">Le app destinate a .NET Framework 4.6 ma che richiedono che il rendering dei controlli WPF venga eseguito mediante l'algoritmo di layout precedente possono aggiungere a questo scopo la riga seguente alla sezione `<runtime>` del file app.config:</span><span class="sxs-lookup"><span data-stu-id="edf79-112">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="edf79-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edf79-113">See also</span></span>

- [<span data-ttu-id="edf79-114">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="edf79-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
