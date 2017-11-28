---
title: Cenni preliminari sul controllo TrackBar (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ccea982c45ab22a4b2ab81bc80c16dd472144bbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="trackbar-control-overview-windows-forms"></a><span data-ttu-id="d80d4-102">Cenni preliminari sul controllo TrackBar (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="d80d4-102">TrackBar Control Overview (Windows Forms)</span></span>
<span data-ttu-id="d80d4-103">Windows Form <xref:System.Windows.Forms.TrackBar> controllo (talvolta definito "slider") viene utilizzato per spostarsi di una grande quantità di informazioni o per visivamente un'impostazione numerica.</span><span class="sxs-lookup"><span data-stu-id="d80d4-103">The Windows Forms <xref:System.Windows.Forms.TrackBar> control (also sometimes called a "slider" control) is used for navigating through a large amount of information or for visually adjusting a numeric setting.</span></span> <span data-ttu-id="d80d4-104">Il <xref:System.Windows.Forms.TrackBar> controllo dispone di due parti: il cursore, noto anche come un dispositivo di scorrimento e i segni di graduazione.</span><span class="sxs-lookup"><span data-stu-id="d80d4-104">The <xref:System.Windows.Forms.TrackBar> control has two parts: the thumb, also known as a slider, and the tick marks.</span></span> <span data-ttu-id="d80d4-105">Il cursore è la parte che può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="d80d4-105">The thumb is the part that can be adjusted.</span></span> <span data-ttu-id="d80d4-106">La posizione corrisponde alla <xref:System.Windows.Forms.TrackBar.Value%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="d80d4-106">Its position corresponds to the <xref:System.Windows.Forms.TrackBar.Value%2A> property.</span></span> <span data-ttu-id="d80d4-107">I segni di graduazione sono indicatori visivi disposti a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="d80d4-107">The tick marks are visual indicators that are spaced at regular intervals.</span></span> <span data-ttu-id="d80d4-108">Controllo trackbar viene spostato ad incrementi specificati dall'utente e possono essere allineate orizzontalmente o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="d80d4-108">The trackbar moves in increments that you specify and can be aligned horizontally or vertically.</span></span> <span data-ttu-id="d80d4-109">Ad esempio, è possibile utilizzare l'indicatore di avanzamento per controllare il cursore intermittente o del mouse la velocità per un sistema.</span><span class="sxs-lookup"><span data-stu-id="d80d4-109">For example, you might use the track bar to control the cursor blink rate or mouse speed for a system.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="d80d4-110">Proprietà chiave</span><span class="sxs-lookup"><span data-stu-id="d80d4-110">Key Properties</span></span>  
 <span data-ttu-id="d80d4-111">Le proprietà della chiave di <xref:System.Windows.Forms.TrackBar> controllo sono <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, e <xref:System.Windows.Forms.TrackBar.Maximum%2A>.</span><span class="sxs-lookup"><span data-stu-id="d80d4-111">The key properties of the <xref:System.Windows.Forms.TrackBar> control are <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, and <xref:System.Windows.Forms.TrackBar.Maximum%2A>.</span></span> <span data-ttu-id="d80d4-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A>è la spaziatura dei segni di graduazione.</span><span class="sxs-lookup"><span data-stu-id="d80d4-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A> is the spacing of the ticks.</span></span> <span data-ttu-id="d80d4-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A>e <xref:System.Windows.Forms.TrackBar.Maximum%2A> sono i valori minimo e massimo che possono essere rappresentati sull'indicatore di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="d80d4-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A> and <xref:System.Windows.Forms.TrackBar.Maximum%2A> are the smallest and largest values that can be represented on the track bar.</span></span>  
  
 <span data-ttu-id="d80d4-114">Altre due proprietà importanti, <xref:System.Windows.Forms.TrackBar.SmallChange%2A> e <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.</span><span class="sxs-lookup"><span data-stu-id="d80d4-114">Two other important properties are <xref:System.Windows.Forms.TrackBar.SmallChange%2A> and <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.</span></span> <span data-ttu-id="d80d4-115">Il valore di <xref:System.Windows.Forms.TrackBar.SmallChange%2A> proprietà è il numero di posizioni, il cursore viene spostato in seguito al pressione dei tasti freccia sinistra o destra.</span><span class="sxs-lookup"><span data-stu-id="d80d4-115">The value of the <xref:System.Windows.Forms.TrackBar.SmallChange%2A> property is the number of positions the thumb moves in response to having the LEFT or RIGHT ARROW key pressed.</span></span> <span data-ttu-id="d80d4-116">Il valore di <xref:System.Windows.Forms.TrackBar.LargeChange%2A> proprietà è il numero di posizioni, il cursore viene spostato in seguito al pressione dei tasti PGSU o PGGIÙ o in risposta a mouse fa clic sull'indicatore di avanzamento su entrambi i lati del cursore.</span><span class="sxs-lookup"><span data-stu-id="d80d4-116">The value of the <xref:System.Windows.Forms.TrackBar.LargeChange%2A> property is the number of positions the thumb moves in response to having the PAGE UP or PAGE DOWN key pressed, or in response to mouse clicks on the track bar on either side of the thumb.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d80d4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d80d4-117">See Also</span></span>  
 <xref:System.Windows.Forms.TrackBar>  
 [<span data-ttu-id="d80d4-118">Controllo TrackBar</span><span class="sxs-lookup"><span data-stu-id="d80d4-118">TrackBar Control</span></span>](../../../../docs/framework/winforms/controls/trackbar-control-windows-forms.md)
