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
# <a name="statusbar-control-overview-windows-forms"></a>Cenni preliminari sul controllo StatusBar (Windows Form)
> [!IMPORTANT]
> I controlli <xref:System.Windows.Forms.StatusStrip> e <xref:System.Windows.Forms.ToolStripStatusLabel> sostituiscono e aggiungono funzionalità ai controlli <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel>; Tuttavia, se si sceglie, i controlli <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro.  
  
 Il Windows Forms [controllo StatusBar](statusbar-control-windows-forms.md) viene usato nei form come area, in genere visualizzata nella parte inferiore di una finestra, in cui un'applicazione può visualizzare vari tipi di informazioni sullo stato. <xref:System.Windows.Forms.StatusBar> controlli possono avere pannelli della barra di stato su di essi che visualizzano testo o icone per indicare lo stato o una serie di icone in un'animazione che indica che un processo funziona; ad esempio, Microsoft Word indica che è in corso il salvataggio del documento.  
  
## <a name="using-the-statusbar-control"></a>Uso del controllo StatusBar  
 Internet Explorer utilizza una barra di stato per indicare l'URL di una pagina quando il mouse viene spostato sul collegamento ipertestuale. Microsoft Word fornisce informazioni sul percorso della pagina, sulla posizione della sezione e sulle modalità di modifica, ad esempio il rilevamento di sovrascrittura e Revisione; e Visual Studio usa la barra di stato per fornire informazioni sensibili al contesto, ad esempio come modificare le finestre ancorabili come ancorate o mobili.  
  
 È possibile visualizzare un singolo messaggio sulla barra di stato impostando la proprietà <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> su `false` (impostazione predefinita) e impostando la proprietà <xref:System.Windows.Forms.StatusBar.Text%2A> della barra di stato sul testo che si desidera visualizzare nella barra di stato. È possibile dividere la barra di stato in pannelli per visualizzare più di un tipo di informazioni impostando la proprietà <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> su `true` e utilizzando il metodo di <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> di <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Procedura: Individuare il pannello selezionato nel controllo StatusBar di Windows Form](determine-which-panel-wf-statusbar-control-was-clicked.md)
