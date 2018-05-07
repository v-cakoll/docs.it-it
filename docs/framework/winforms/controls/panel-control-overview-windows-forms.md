---
title: Cenni preliminari sul controllo Panel (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
ms.openlocfilehash: 1ba766629f923b091459531ce74d28dca4b4ea0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="panel-control-overview-windows-forms"></a>Cenni preliminari sul controllo Panel (Windows Form)
Windows Form <xref:System.Windows.Forms.Panel> controlli vengono utilizzati per fornire un raggruppamento identificabile per altri controlli. In genere, utilizzare i pannelli di suddividere un form dalla funzione. Ad esempio, potrebbe essere un modulo d'ordine che specifica le opzioni di spedizione, ad esempio quali notturno vettore da usare. Raggruppamento di tutte le opzioni in un pannello concede all'utente un'indicazione visiva logica. In fase di progettazione tutti i controlli possono essere spostati facilmente, quando si sposta il <xref:System.Windows.Forms.Panel> controllare tutti i controlli in esso contenuti, troppo spostano. I controlli raggruppati in un pannello è possibile accedere tramite il relativo <xref:System.Windows.Forms.Control.Controls%2A> proprietà. Questa proprietà restituisce una raccolta di <xref:System.Windows.Forms.Control> istanze, pertanto è necessario eseguire il cast di un controllo in genere recuperate in questo modo al relativo tipo specifico.  
  
## <a name="panel-versus-groupbox"></a>Pannello rispetto al controllo GroupBox  
 Il <xref:System.Windows.Forms.Panel> è simile al controllo il <xref:System.Windows.Forms.GroupBox> controllo, tuttavia, solo il <xref:System.Windows.Forms.Panel> controllo può contenere barre di scorrimento e solo il <xref:System.Windows.Forms.GroupBox> controllo Visualizza una didascalia.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Per visualizzare le barre di scorrimento, impostare il <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> proprietà `true`. È anche possibile personalizzare l'aspetto del pannello impostando il <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, e <xref:System.Windows.Forms.Panel.BorderStyle%2A> proprietà. Per ulteriori informazioni sul <xref:System.Windows.Forms.Control.BackColor%2A> e <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà, vedere [procedura: impostare lo sfondo di un pannello](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md). Il <xref:System.Windows.Forms.Panel.BorderStyle%2A> proprietà determina se il pannello è delineato da alcun bordo visibile (<xref:System.Windows.Forms.BorderStyle.None>), una linea semplice (<xref:System.Windows.Forms.BorderStyle.FixedSingle>), o una linea ombreggiata (<xref:System.Windows.Forms.BorderStyle.Fixed3D>).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Panel>  
 [Controllo GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)  
 [Procedura: Raggruppare i controlli con il controllo Panel di Windows Form nella finestra di progettazione](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)  
 [Procedura: Impostare lo sfondo di un controllo Panel di Windows Form con la finestra di progettazione](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
