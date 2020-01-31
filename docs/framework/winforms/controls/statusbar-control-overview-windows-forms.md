---
title: Cenni preliminari sul controllo StatusBar
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: b0b97bc3cb0291871e1fd113d82d0b480b53cdba
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742872"
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="b3fe4-102">Cenni preliminari sul controllo StatusBar (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="b3fe4-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="b3fe4-103">I controlli <xref:System.Windows.Forms.StatusStrip> e <xref:System.Windows.Forms.ToolStripStatusLabel> sostituiscono e aggiungono funzionalità ai controlli <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel>; Tuttavia, se si sceglie, i controlli <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="b3fe4-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="b3fe4-104">Il Windows Forms [controllo StatusBar](statusbar-control-windows-forms.md) viene usato nei form come area, in genere visualizzata nella parte inferiore di una finestra, in cui un'applicazione può visualizzare vari tipi di informazioni sullo stato.</span><span class="sxs-lookup"><span data-stu-id="b3fe4-104">The Windows Forms [StatusBar Control](statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="b3fe4-105"><xref:System.Windows.Forms.StatusBar> controlli possono avere pannelli della barra di stato su di essi che visualizzano testo o icone per indicare lo stato o una serie di icone in un'animazione che indica che un processo funziona; ad esempio, Microsoft Word indica che è in corso il salvataggio del documento.</span><span class="sxs-lookup"><span data-stu-id="b3fe4-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="b3fe4-106">Uso del controllo StatusBar</span><span class="sxs-lookup"><span data-stu-id="b3fe4-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="b3fe4-107">Internet Explorer utilizza una barra di stato per indicare l'URL di una pagina quando il mouse viene spostato sul collegamento ipertestuale. Microsoft Word fornisce informazioni sul percorso della pagina, sulla posizione della sezione e sulle modalità di modifica, ad esempio il rilevamento di sovrascrittura e Revisione; e Visual Studio usa la barra di stato per fornire informazioni sensibili al contesto, ad esempio come modificare le finestre ancorabili come ancorate o mobili.</span><span class="sxs-lookup"><span data-stu-id="b3fe4-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; Microsoft Word gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="b3fe4-108">È possibile visualizzare un singolo messaggio sulla barra di stato impostando la proprietà <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> su `false` (impostazione predefinita) e impostando la proprietà <xref:System.Windows.Forms.StatusBar.Text%2A> della barra di stato sul testo che si desidera visualizzare nella barra di stato.</span><span class="sxs-lookup"><span data-stu-id="b3fe4-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="b3fe4-109">È possibile dividere la barra di stato in pannelli per visualizzare più di un tipo di informazioni impostando la proprietà <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> su `true` e utilizzando il metodo di <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> di <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span><span class="sxs-lookup"><span data-stu-id="b3fe4-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3fe4-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3fe4-110">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="b3fe4-111">Procedura: Individuare il pannello selezionato nel controllo StatusBar di Windows Form</span><span class="sxs-lookup"><span data-stu-id="b3fe4-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
