---
title: Cenni preliminari sul controllo StatusBar (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: 4e1816ef221641f5ad54fb429442ed43289b592a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505430"
---
# <a name="statusbar-control-overview-windows-forms"></a>Cenni preliminari sul controllo StatusBar (Windows Form)
> [!IMPORTANT]
>  Il <xref:System.Windows.Forms.StatusStrip> e <xref:System.Windows.Forms.ToolStripStatusLabel> controlli sostituire e aggiungano funzionalità rispetto al <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> controlli; tuttavia, il <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> controlli vengono mantenuti per compatibilità con le versioni precedenti e per un uso futuro, se si Scegliere.  
  
 I moduli di Windows [controllo StatusBar](statusbar-control-windows-forms.md) viene usato nei form come un'area, in genere visualizzata nella parte inferiore di una finestra, in cui un'applicazione può visualizzare vari tipi di informazioni sullo stato. <xref:System.Windows.Forms.StatusBar> i controlli possono avere pannelli della barra di stato su di essi che visualizzano testo o icone per indicare lo stato o una serie di icone per indicare che un processo viene eseguito; un'animazione ad esempio, Microsoft Word che indica che il documento è in corso salvato.  
  
## <a name="using-the-statusbar-control"></a>Utilizzo del controllo StatusBar  
 Internet Explorer utilizza una barra di stato per indicare l'URL di una pagina quando il mouse si sposta sul collegamento ipertestuale. Microsoft Word fornisce informazioni sul percorso della pagina, la sezione e le modalità, ad esempio la sovrascrittura e revisioni; rilevamento di modifica e Visual Studio Usa la barra di stato per fornire informazioni sensibili al contesto, ad esempio indicante come modificare finestre ancorabili come ancorato o mobile.  
  
 È possibile visualizzare un singolo messaggio sulla barra di stato tramite l'impostazione di <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> proprietà `false` (predefinito) e impostando il <xref:System.Windows.Forms.StatusBar.Text%2A> proprietà della barra di stato per il testo da visualizzare nella barra di stato. È possibile dividere la barra di stato in pannelli per visualizzare più di un tipo di informazioni mediante l'impostazione il <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> proprietà `true` e usando la <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> metodo di <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Procedura: Individuare il pannello nel controllo StatusBar Windows Form è stato selezionato](determine-which-panel-wf-statusbar-control-was-clicked.md)
