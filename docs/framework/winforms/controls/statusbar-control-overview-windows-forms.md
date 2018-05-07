---
title: Cenni preliminari sul controllo StatusBar (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: 6dd5b45b38ec4fb04d9a53a1648cfe6e5a5b9f20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="statusbar-control-overview-windows-forms"></a>Cenni preliminari sul controllo StatusBar (Windows Form)
> [!IMPORTANT]
>  Il <xref:System.Windows.Forms.StatusStrip> e <xref:System.Windows.Forms.ToolStripStatusLabel> controlli sostituire e aggiungere funzionalità a di <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> controlli; tuttavia, il <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> vengono mantenuti per compatibilità con le versioni precedenti e per utilizzo futuro, se si Scegliere.  
  
 Windows Form [controllo StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) viene usato nei form come un'area solitamente rappresentata nella parte inferiore di una finestra, in cui un'applicazione può visualizzare vari tipi di informazioni sullo stato. <xref:System.Windows.Forms.StatusBar> i controlli possono avere pannelli della barra di stato su di essi che visualizzano testo o icone per indicare lo stato o una serie di icone un'animazione per indicare che un processo è in corso; ad esempio, [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] che indica che viene salvato il documento.  
  
## <a name="using-the-statusbar-control"></a>Utilizzo del controllo StatusBar  
 Internet Explorer utilizza una barra di stato per indicare l'URL di una pagina quando il mouse viene posizionato su un collegamento ipertestuale; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] fornisce informazioni sul percorso della pagina, la sezione posizione e le modalità di modifica, ad esempio la sovrascrittura e il rilevamento delle revisioni e Visual Studio utilizza la barra di stato per fornire le informazioni sensibili al contesto, ad esempio possibile decifrare i suggerimenti su come utilizzare finestre ancorabili come ancorato o mobile.  
  
 È possibile visualizzare un singolo messaggio sulla barra di stato impostando il <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> proprietà `false` (predefinito) e impostando il <xref:System.Windows.Forms.StatusBar.Text%2A> proprietà della barra di stato per il testo da visualizzare nella barra di stato. È possibile dividere la barra di stato in pannelli per visualizzare più di un tipo di informazioni mediante l'impostazione di <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> proprietà `true` e utilizzando il <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> metodo di <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [Procedura: Individuare il pannello selezionato nel controllo StatusBar di Windows Form](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)
