---
title: Cenni preliminari sul controllo TableLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- TableLayoutPanel
helpviewer_keywords:
- controls [Windows Forms], resizing
- resizable controls [Windows Forms]
- Windows Forms controls, proportional resizing
- Windows Forms, proportional resizing of controls
- layout [Windows Forms], TableLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
ms.assetid: 337661c8-61cb-44ee-93e0-3662bddec327
ms.openlocfilehash: be7ef4055d809349fe97a3d48e29158c5449576b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43419829"
---
# <a name="tablelayoutpanel-control-overview"></a>Cenni preliminari sul controllo TableLayoutPanel
Il controllo <xref:System.Windows.Forms.TableLayoutPanel> dispone il contenuto in una griglia. Poiché il layout viene effettuato sia in fase di progettazione che in fase di esecuzione, può cambiare dinamicamente in base alle modifiche dell'ambiente di applicazione, consentendo il ridimensionamento proporzionale dei controlli presenti nel pannello in risposta a modifiche quali il ridimensionamento del controllo padre o la variazione della lunghezza del testo dovuta alla localizzazione.  
  
 Qualsiasi controllo Windows Form può essere figlio del controllo <xref:System.Windows.Forms.TableLayoutPanel>, tra cui altre istanze di <xref:System.Windows.Forms.TableLayoutPanel>, consentendo la creazione di layout sofisticati che si adattano alle modifiche in fase di esecuzione.  
  
 Il controllo <xref:System.Windows.Forms.TableLayoutPanel> può espandersi per contenere nuovi controlli aggiunti, a seconda del valore delle proprietà <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> e <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A>. L'impostazione della proprietà <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> o <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> su 0 indica che il controllo <xref:System.Windows.Forms.TableLayoutPanel> non è limitato nella direzione corrispondente.  
  
 È anche possibile controllare la direzione di espansione, orizzontale o verticale, per quando il controllo <xref:System.Windows.Forms.TableLayoutPanel> non riesce più a contenere i controlli figlio. Per impostazione predefinita, il controllo <xref:System.Windows.Forms.TableLayoutPanel> si espande verso il basso aggiungendo delle righe.  
  
 Per modificare il comportamento predefinito di righe e colonne, impostare le proprietà di righe e colonne mediante <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> e <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>. Le proprietà delle righe possono essere impostate separatamente da quelle delle colonne.  
  
 Il controllo <xref:System.Windows.Forms.TableLayoutPanel> aggiunge ai propri controlli figlio le proprietà `Cell`, `Column`. `Row`, `ColumnSpan` e `RowSpan`.  
  
 Per unire le celle nel controllo <xref:System.Windows.Forms.TableLayoutPanel>, impostare la proprietà `ColumnSpan` o `RowSpan` in un controllo figlio.  
  
1.  [Procedura: Allineare ed estendere un controllo in un controllo TableLayoutPanel](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2.  [Procedura: Inserire righe e colonne in un controllo TableLayoutPanel](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
3.  [Procedura: Modificare colonne e righe in un controllo TableLayoutPanel](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
4.  [Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](https://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 [Procedura: Progettare un layout di Windows Form che risponda correttamente alla localizzazione](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [Procedura: Creare un Windows Form ridimensionabile per immissione dati](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)  
 [Procedure consigliate per il controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)
