---
title: Cenni preliminari sul controllo ToolStripContainer
ms.date: 03/30/2017
f1_keywords:
- ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
ms.openlocfilehash: 1f8d8bf8edd7968ed2d2a5c4ddd654dccf318f71
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654048"
---
# <a name="toolstripcontainer-control-overview"></a>Cenni preliminari sul controllo ToolStripContainer
Oggetto <xref:System.Windows.Forms.ToolStripContainer> contiene dei pannelli sui relativi a sinistra, destra, superiore e inferiore per posizionare e raggruppare <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, e <xref:System.Windows.Forms.StatusStrip> controlli. Più controlli <xref:System.Windows.Forms.ToolStrip> vengono raggruppati verticalmente se li si inserisce nell'oggetto <xref:System.Windows.Forms.ToolStripContainer> di sinistra o di destra. Vengono raggruppati orizzontalmente se li si inserisce nell'oggetto <xref:System.Windows.Forms.ToolStripContainer> in alto o in basso. È possibile usare l'oggetto <xref:System.Windows.Forms.ToolStripContentPanel> centrale di <xref:System.Windows.Forms.ToolStripContainer> per posizionare i tradizionali controlli sul form.  
  
 Alcuni o tutti i controlli <xref:System.Windows.Forms.ToolStripContainer> sono direttamente selezionabili in fase di progettazione e possono essere eliminati. Ogni pannello di un <xref:System.Windows.Forms.ToolStripContainer> è espandibile e comprimibile e viene ridimensionato con i controlli in esso contenuti.  
  
### <a name="important-toolstripcontainer-members"></a>Membri importanti ToolStripContainer  
  
|nome|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|Ottiene il pannello inferiore del <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|Ottiene o imposta un valore che indica se il pannello inferiore del <xref:System.Windows.Forms.ToolStripContainer> è visibile.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|Ottiene il pannello sinistro del <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|Ottiene o imposta un valore che indica se il pannello sinistro del <xref:System.Windows.Forms.ToolStripContainer> è visibile.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|Ottiene il pannello destro del <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|Ottiene o imposta un valore che indica se il pannello destro del <xref:System.Windows.Forms.ToolStripContainer> è visibile.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|Ottiene il pannello superiore del <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|Ottiene o imposta un valore che indica se il pannello superiore del <xref:System.Windows.Forms.ToolStripContainer> è visibile.|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.ToolStripContainer>
- <xref:System.Windows.Forms.ToolStripContentPanel>
