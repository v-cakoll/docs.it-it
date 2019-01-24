---
title: "Procedura: Impostare l'unione automatica dei Menu per applicazioni MDI"
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 3aeaf9ee4818b6689905c10d2bd46fc887609c35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549824"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>Procedura: Impostare l'unione automatica dei Menu per applicazioni MDI
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
- [Panoramica sul controllo MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
