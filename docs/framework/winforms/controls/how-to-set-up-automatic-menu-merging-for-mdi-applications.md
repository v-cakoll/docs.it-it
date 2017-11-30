---
title: 'Procedura: impostare l''unione automatica dei menu per applicazioni MDI'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e99aed38ed6c3af3424c264631f0eaf27e46af7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>Procedura: impostare l'unione automatica dei menu per applicazioni MDI
La procedura seguente fornisce i passaggi di base per la configurazione di unione automatica in un'applicazione con interfaccia a documenti multipli (MDI) con <xref:System.Windows.Forms.MenuStrip>.  
  
### <a name="to-set-up-automatic-menu-merging"></a>Per impostare l'unione automatica dei menu  
  
1.  Creare il form padre MDI impostando il relativo <xref:System.Windows.Forms.Form.IsMdiContainer%2A> proprietà `true`.  
  
2.  Aggiungere un <xref:System.Windows.Forms.MenuStrip> il padre MDI, impostando il relativo <xref:System.Windows.Forms.Form.MainMenuStrip%2A> che proprietà <xref:System.Windows.Forms.MenuStrip>.  
  
3.  Creare un form figlio MDI e impostare il relativo <xref:System.Windows.Forms.Form.MdiParent%2A> proprietà sul nome del form padre.  
  
4.  Aggiungere un <xref:System.Windows.Forms.MenuStrip> per il form figlio MDI.  
  
5.  Nel form figlio, impostare il <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà del <xref:System.Windows.Forms.MenuStrip> a `false`.  
  
6.  Aggiungere le voci di menu del form figlio <xref:System.Windows.Forms.MenuStrip> che si desidera unire il form padre <xref:System.Windows.Forms.MenuStrip> quando è attivato il form figlio.  
  
7.  Utilizzare il <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> proprietà dal menu di elementi del form figlio <xref:System.Windows.Forms.MenuStrip> per controllare la modalità di unione nel form padre.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Panoramica sul controllo MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
