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
# <a name="statusbar-control-overview-windows-forms"></a>Cenni preliminari sul controllo StatusBar (Windows Form)
> [!IMPORTANT]
>  Il <xref:System.Windows.Forms.StatusStrip> e <xref:System.Windows.Forms.ToolStripStatusLabel> controlli sostituire e aggiungere funzionalità a di <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> controlli; tuttavia, il <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> vengono mantenuti per compatibilità con le versioni precedenti e per utilizzo futuro, se si Scegliere.  
  
 Windows Form [controllo StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) viene usato nei form come un'area solitamente rappresentata nella parte inferiore di una finestra, in cui un'applicazione può visualizzare vari tipi di informazioni sullo stato. <xref:System.Windows.Forms.StatusBar>controlli che possono disporre pannelli della barra di stato su di essi che visualizzano testo o icone per indicare lo stato o una serie di icone per indicare che un processo è in corso; un'animazione ad esempio, [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] che indica che il documento viene salvato.  
  
## <a name="using-the-statusbar-control"></a>Utilizzo del controllo StatusBar  
 Internet Explorer utilizza una barra di stato per indicare l'URL di una pagina quando il mouse si sposta sul collegamento ipertestuale. [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] fornisce informazioni sul percorso della pagina, la sezione posizione e le modalità, ad esempio la sovrascrittura e; il rilevamento delle revisioni di modifica e [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] utilizza la barra di stato per fornire informazioni sensibili al contesto, ad esempio relativo a come modificare ancorabile Windows come ancorato o mobile.  
  
 È possibile visualizzare un singolo messaggio sulla barra di stato impostando il <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> proprietà `false` (predefinito) e impostando il <xref:System.Windows.Forms.StatusBar.Text%2A> proprietà della barra di stato per il testo da visualizzare nella barra di stato. È possibile dividere la barra di stato in pannelli per visualizzare più di un tipo di informazioni mediante l'impostazione di <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> proprietà `true` e utilizzando il <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> metodo di <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [Procedura: Individuare il pannello selezionato nel controllo StatusBar di Windows Form](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)
