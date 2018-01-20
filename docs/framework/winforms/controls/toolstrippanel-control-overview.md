---
title: Cenni preliminari sul controllo ToolStripPanel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ToolStripPanel
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms], about ToolStripPanel control
ms.assetid: ce54a60c-5eba-4b4c-bd77-cf0748a666cc
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d376b5df4fabf63a87be04eca01136e22b3e3f82
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="toolstrippanel-control-overview"></a><span data-ttu-id="228c8-102">Cenni preliminari sul controllo ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="228c8-102">ToolStripPanel Control Overview</span></span>
<span data-ttu-id="228c8-103">Oggetto <xref:System.Windows.Forms.ToolStripPanel> fornisce un'unica area per il posizionamento e raggruppamento verticale/orizzontale <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, e <xref:System.Windows.Forms.StatusStrip> controlli.</span><span class="sxs-lookup"><span data-stu-id="228c8-103">A <xref:System.Windows.Forms.ToolStripPanel> provides a single area for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="228c8-104">Più <xref:System.Windows.Forms.ToolStrip> controlli vengono disposti orizzontalmente o verticalmente in base il <xref:System.Windows.Forms.ToolStripPanelRow.Orientation%2A> del <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="228c8-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically or horizontally depending on the <xref:System.Windows.Forms.ToolStripPanelRow.Orientation%2A> of the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>  
  
### <a name="important-toolstrippanel-members"></a><span data-ttu-id="228c8-105">Membri importanti di ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="228c8-105">Important ToolStripPanel Members</span></span>  
  
|<span data-ttu-id="228c8-106">nome</span><span class="sxs-lookup"><span data-stu-id="228c8-106">Name</span></span>|<span data-ttu-id="228c8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="228c8-107">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripPanel.Orientation%2A>|<span data-ttu-id="228c8-108">Ottiene o imposta un valore che indica l'orientamento orizzontale o verticale del <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="228c8-108">Gets or sets a value indicating the horizontal or vertical orientation of the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.Renderer%2A>|<span data-ttu-id="228c8-109">Ottiene o imposta un <xref:System.Windows.Forms.ToolStripRenderer> consentono di personalizzare l'aspetto di un <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="228c8-109">Gets or sets a <xref:System.Windows.Forms.ToolStripRenderer> used to customize the appearance of a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.RenderMode%2A>|<span data-ttu-id="228c8-110">Ottiene o imposta gli stili di disegno da applicare per il <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="228c8-110">Gets or sets the painting styles to be applied to the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.RowMargin%2A>|<span data-ttu-id="228c8-111">Ottiene o imposta la spaziatura, in pixel, tra il <xref:System.Windows.Forms.ToolStripPanelRow> e <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="228c8-111">Gets or sets the spacing, in pixels, between the <xref:System.Windows.Forms.ToolStripPanelRow> and the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.Rows%2A>|<span data-ttu-id="228c8-112">Ottiene il <xref:System.Windows.Forms.ToolStripPanelRow> in questo <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="228c8-112">Gets the <xref:System.Windows.Forms.ToolStripPanelRow> in this <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.Join%2A>|<span data-ttu-id="228c8-113">Aggiunge un <xref:System.Windows.Forms.ToolStrip> per un <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="228c8-113">Adds a <xref:System.Windows.Forms.ToolStrip> to a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="228c8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="228c8-114">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 <xref:System.Windows.Forms.ToolStripContentPanel>  
 [<span data-ttu-id="228c8-115">Esempio di ToolStrip</span><span class="sxs-lookup"><span data-stu-id="228c8-115">ToolStrip Sample</span></span>](http://msdn.microsoft.com/library/b7352439-184a-4a3a-b2ad-07465d3af9ed)
