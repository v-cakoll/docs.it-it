---
title: "Procedura: Configurare l'unione automatica dei menu per applicazioni con interfaccia a documenti multipli"
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 17edde6e3968823abc915eb5faed6d2751ed9393
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129356"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>Procedura: Configurare l'unione automatica dei menu per applicazioni con interfaccia a documenti multipli
La procedura seguente contiene i passaggi di base per la configurazione di unione automatica in un'applicazione di interfaccia a documenti multipli (MDI) con <xref:System.Windows.Forms.MenuStrip>.  
  
### <a name="to-set-up-automatic-menu-merging"></a>Per impostare l'unione automatica dei menu  
  
1.  Creare il form padre MDI impostando relativi <xref:System.Windows.Forms.Form.IsMdiContainer%2A> proprietà `true`.  
  
2.  Aggiungere un <xref:System.Windows.Forms.MenuStrip> all'elemento padre MDI, l'impostazione relativa <xref:System.Windows.Forms.Form.MainMenuStrip%2A> proprietà a cui <xref:System.Windows.Forms.MenuStrip>.  
  
3.  Creare un form figlio MDI e impostare il <xref:System.Windows.Forms.Form.MdiParent%2A> proprietà sul nome del form padre.  
  
4.  Aggiungere un <xref:System.Windows.Forms.MenuStrip> per form figlio MDI.  
  
5.  Nel form figlio, impostare il <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà del <xref:System.Windows.Forms.MenuStrip> a `false`.  
  
6.  Aggiungere le voci di menu del modulo figlio <xref:System.Windows.Forms.MenuStrip> che si desidera unire il form padre <xref:System.Windows.Forms.MenuStrip> quando viene attivato il form figlio.  
  
7.  Usare la <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> gli elementi proprietà dal menu del form figlio <xref:System.Windows.Forms.MenuStrip> per controllare la modalità di unione in form padre.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Panoramica del controllo MenuStrip](menustrip-control-overview-windows-forms.md)
