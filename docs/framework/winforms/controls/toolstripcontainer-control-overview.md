---
title: Cenni preliminari sul controllo ToolStripContainer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a1a4c9c77e1f347f95c0a5e17ab0d37e0013d6b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="toolstripcontainer-control-overview"></a>Cenni preliminari sul controllo ToolStripContainer
Oggetto <xref:System.Windows.Forms.ToolStripContainer> contiene dei pannelli sui relativi sinistro, destro, superiore e inferiore per posizionare e raggruppare <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, e <xref:System.Windows.Forms.StatusStrip> controlli. Più controlli <xref:System.Windows.Forms.ToolStrip> vengono raggruppati verticalmente se li si inserisce nell'oggetto <xref:System.Windows.Forms.ToolStripContainer> di sinistra o di destra. Vengono raggruppati orizzontalmente se li si inserisce nell'oggetto <xref:System.Windows.Forms.ToolStripContainer> in alto o in basso. È possibile usare l'oggetto <xref:System.Windows.Forms.ToolStripContentPanel> centrale di <xref:System.Windows.Forms.ToolStripContainer> per posizionare i tradizionali controlli sul form.  
  
 Alcuni o tutti i controlli <xref:System.Windows.Forms.ToolStripContainer> sono direttamente selezionabili in fase di progettazione e possono essere eliminati. Ogni pannello di un <xref:System.Windows.Forms.ToolStripContainer> è espandibile e comprimibile e viene ridimensionato con i controlli in esso contenuti.  
  
### <a name="important-toolstripcontainer-members"></a>Membri importanti di ToolStripContainer  
  
|nome|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|Ottiene il pannello inferiore del <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|Ottiene o imposta un valore che indica se il riquadro inferiore del <xref:System.Windows.Forms.ToolStripContainer> è visibile.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|Ottiene il pannello di sinistra di <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|Ottiene o imposta un valore che indica se il riquadro sinistro del <xref:System.Windows.Forms.ToolStripContainer> è visibile.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|Ottiene il pannello di destra la <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|Ottiene o imposta un valore che indica se il riquadro destro del <xref:System.Windows.Forms.ToolStripContainer> è visibile.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|Ottiene il riquadro superiore del <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|Ottiene o imposta un valore che indica se il riquadro superiore del <xref:System.Windows.Forms.ToolStripContainer> è visibile.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolStripContainer>  
 <xref:System.Windows.Forms.ToolStripContentPanel>
