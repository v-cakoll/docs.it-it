---
title: Cenni preliminari sul controllo StatusBar (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: df8e6b8484cf3b35c684445445ddc41adc358698
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="5b9d0-102">Cenni preliminari sul controllo StatusBar (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="5b9d0-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="5b9d0-103">Il <xref:System.Windows.Forms.StatusStrip> e <xref:System.Windows.Forms.ToolStripStatusLabel> controlli sostituire e aggiungere funzionalità a di <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> controlli; tuttavia, il <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> vengono mantenuti per compatibilità con le versioni precedenti e per utilizzo futuro, se si Scegliere.</span><span class="sxs-lookup"><span data-stu-id="5b9d0-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="5b9d0-104">Windows Form [controllo StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) viene usato nei form come un'area solitamente rappresentata nella parte inferiore di una finestra, in cui un'applicazione può visualizzare vari tipi di informazioni sullo stato.</span><span class="sxs-lookup"><span data-stu-id="5b9d0-104">The Windows Forms [StatusBar Control](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="5b9d0-105"><xref:System.Windows.Forms.StatusBar>controlli che possono disporre pannelli della barra di stato su di essi che visualizzano testo o icone per indicare lo stato o una serie di icone per indicare che un processo è in corso; un'animazione ad esempio, [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] che indica che il documento viene salvato.</span><span class="sxs-lookup"><span data-stu-id="5b9d0-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="5b9d0-106">Utilizzo del controllo StatusBar</span><span class="sxs-lookup"><span data-stu-id="5b9d0-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="5b9d0-107">Internet Explorer utilizza una barra di stato per indicare l'URL di una pagina quando il mouse si sposta sul collegamento ipertestuale. [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] fornisce informazioni sul percorso della pagina, la sezione posizione e le modalità, ad esempio la sovrascrittura e; il rilevamento delle revisioni di modifica e [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] utilizza la barra di stato per fornire informazioni sensibili al contesto, ad esempio relativo a come modificare ancorabile Windows come ancorato o mobile.</span><span class="sxs-lookup"><span data-stu-id="5b9d0-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] gives you information on page location, section location, and editing modes such as overtype and revision tracking; and [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="5b9d0-108">È possibile visualizzare un singolo messaggio sulla barra di stato impostando il <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> proprietà `false` (predefinito) e impostando il <xref:System.Windows.Forms.StatusBar.Text%2A> proprietà della barra di stato per il testo da visualizzare nella barra di stato.</span><span class="sxs-lookup"><span data-stu-id="5b9d0-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="5b9d0-109">È possibile dividere la barra di stato in pannelli per visualizzare più di un tipo di informazioni mediante l'impostazione di <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> proprietà `true` e utilizzando il <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> metodo di <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span><span class="sxs-lookup"><span data-stu-id="5b9d0-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b9d0-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b9d0-110">See Also</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [<span data-ttu-id="5b9d0-111">Procedura: Individuare il pannello selezionato nel controllo StatusBar di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5b9d0-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)
