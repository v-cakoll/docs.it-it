---
title: Cenni preliminari sul controllo ToolStripProgressBar
ms.date: 03/30/2017
f1_keywords:
- ToolStripProgressBar
helpviewer_keywords:
- toolbars [Windows Forms], progress bars
- progress controls [Windows Forms]
- ToolStripProgressBar control [Windows Forms], about ToolStripProgressBar control
ms.assetid: ec3ab522-5fe4-4b4d-a551-bc19e84f4774
ms.openlocfilehash: 57a8c61c71fa17e1d3df309007823eab76d9efb1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528628"
---
# <a name="toolstripprogressbar-control-overview"></a><span data-ttu-id="b67e1-102">Cenni preliminari sul controllo ToolStripProgressBar</span><span class="sxs-lookup"><span data-stu-id="b67e1-102">ToolStripProgressBar Control Overview</span></span>
<span data-ttu-id="b67e1-103">Il <xref:System.Windows.Forms.ToolStripProgressBar> combina il raggruppamento verticale/orizzontale e le funzionalità di rendering di tutte le <xref:System.Windows.Forms.ToolStrip> controlli con la tipica funzionalità di rilevamento di processo.</span><span class="sxs-lookup"><span data-stu-id="b67e1-103">The <xref:System.Windows.Forms.ToolStripProgressBar> combines the rafting and rendering functionality of all <xref:System.Windows.Forms.ToolStrip> controls with its typical process-tracking functionality.</span></span> <span data-ttu-id="b67e1-104">Oggetto <xref:System.Windows.Forms.ToolStripProgressBar> è generalmente ospitato da <xref:System.Windows.Forms.StatusStrip>e meno frequentemente in un <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="b67e1-104">A <xref:System.Windows.Forms.ToolStripProgressBar> is most usually hosted by <xref:System.Windows.Forms.StatusStrip>, and less frequently by a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="b67e1-105">Sebbene <xref:System.Windows.Forms.ToolStripProgressBar> sostituisce e aggiunge funzionalità al controllo nelle versioni precedenti, <xref:System.Windows.Forms.ToolStripProgressBar> viene mantenuto per compatibilità con le versioni precedenti e per un uso futuro, se si desidera.</span><span class="sxs-lookup"><span data-stu-id="b67e1-105">Although <xref:System.Windows.Forms.ToolStripProgressBar> replaces and adds functionality to the control in previous versions, <xref:System.Windows.Forms.ToolStripProgressBar> is retained for both backward compatibility and future use if desired.</span></span>  
  
### <a name="important-toolstripprogressbar-members"></a><span data-ttu-id="b67e1-106">Membri importanti ToolStripProgressBar</span><span class="sxs-lookup"><span data-stu-id="b67e1-106">Important ToolStripProgressBar Members</span></span>  
  
|<span data-ttu-id="b67e1-107">nome</span><span class="sxs-lookup"><span data-stu-id="b67e1-107">Name</span></span>|<span data-ttu-id="b67e1-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b67e1-108">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripProgressBar.MarqueeAnimationSpeed%2A>|<span data-ttu-id="b67e1-109">Ottiene o imposta un valore che rappresenta il ritardo tra ogni <xref:System.Windows.Forms.ProgressBarStyle.Marquee> aggiornamento, della visualizzazione in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="b67e1-109">Gets or sets a value representing the delay between each <xref:System.Windows.Forms.ProgressBarStyle.Marquee> display update, in milliseconds.</span></span>|  
|<xref:System.Windows.Forms.ProgressBar.Maximum%2A>|<span data-ttu-id="b67e1-110">Ottiene o imposta il limite superiore dell'intervallo definito per questo <xref:System.Windows.Forms.ToolStripProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="b67e1-110">Gets or sets the upper bound of the range that is defined for this <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Minimum%2A>|<span data-ttu-id="b67e1-111">Ottiene o imposta il limite inferiore dell'intervallo definito per questo <xref:System.Windows.Forms.ToolStripProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="b67e1-111">Gets or sets the lower bound of the range that is defined for this <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Style%2A>|<span data-ttu-id="b67e1-112">Ottiene o imposta lo stile a cui il <xref:System.Windows.Forms.ToolStripProgressBar> viene usato per visualizzare lo stato di avanzamento di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="b67e1-112">Gets or sets the style that the <xref:System.Windows.Forms.ToolStripProgressBar> uses to display the progress of an operation.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Value%2A>|<span data-ttu-id="b67e1-113">Ottiene o imposta il valore corrente del <xref:System.Windows.Forms.ToolStripProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="b67e1-113">Gets or sets the current value of the <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.PerformStep%2A>|<span data-ttu-id="b67e1-114">Fa avanzare la posizione corrente dell'indicatore di stato la quantità di <xref:System.Windows.Forms.ToolStripProgressBar.Step%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b67e1-114">Advances the current position of the progress bar by the amount of the <xref:System.Windows.Forms.ToolStripProgressBar.Step%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b67e1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b67e1-115">See also</span></span>
- <xref:System.Windows.Forms.ToolStripProgressBar>
