---
title: Cenni preliminari sul controllo StatusBar (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: bd58d4c70e3a3c88e57fe242957f669d1944fd71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964427"
---
# <a name="statusbar-control-overview-windows-forms"></a>Cenni preliminari sul controllo StatusBar (Windows Form)
> [!IMPORTANT]
> I <xref:System.Windows.Forms.StatusStrip> controlli <xref:System.Windows.Forms.ToolStripStatusLabel> e <xref:System.Windows.Forms.StatusBar> sostituiscono e aggiungono funzionalità ai <xref:System.Windows.Forms.StatusBarPanel> controlli e; tuttavia, <xref:System.Windows.Forms.StatusBar> i <xref:System.Windows.Forms.StatusBarPanel> controlli e vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro, se scegliere.  
  
 Il Windows Forms [controllo StatusBar](statusbar-control-windows-forms.md) viene usato nei form come area, in genere visualizzata nella parte inferiore di una finestra, in cui un'applicazione può visualizzare vari tipi di informazioni sullo stato. <xref:System.Windows.Forms.StatusBar>i controlli possono avere pannelli della barra di stato su di essi che visualizzano testo o icone per indicare lo stato o una serie di icone in un'animazione che indica che un processo funziona; ad esempio, Microsoft Word indica che è in corso il salvataggio del documento.  
  
## <a name="using-the-statusbar-control"></a>Uso del controllo StatusBar  
 Internet Explorer utilizza una barra di stato per indicare l'URL di una pagina quando il mouse viene spostato sul collegamento ipertestuale. Microsoft Word fornisce informazioni sul percorso della pagina, sulla posizione della sezione e sulle modalità di modifica, ad esempio il rilevamento di sovrascrittura e Revisione; e Visual Studio usa la barra di stato per fornire informazioni sensibili al contesto, ad esempio come modificare le finestre ancorabili come ancorate o mobili.  
  
 È possibile visualizzare un singolo messaggio sulla barra di stato impostando la <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> proprietà su `false` (impostazione predefinita) e impostando <xref:System.Windows.Forms.StatusBar.Text%2A> la proprietà della barra di stato sul testo che si desidera visualizzare nella barra di stato. È possibile dividere la barra di stato in pannelli per visualizzare più di un tipo di informazioni impostando <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> la proprietà `true` su e usando <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> il metodo <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>di.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Procedura: Determinare il pannello in cui è stato fatto clic sul controllo Windows Forms StatusBar](determine-which-panel-wf-statusbar-control-was-clicked.md)
