---
title: Cenni preliminari sul controllo Panel (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
ms.openlocfilehash: d4976b3725d04162ac10242c486f57c4d2598769
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012685"
---
# <a name="panel-control-overview-windows-forms"></a>Cenni preliminari sul controllo Panel (Windows Form)
Windows Form <xref:System.Windows.Forms.Panel> controlli vengono usati per fornire un raggruppamento identificabile per gli altri controlli. In genere, si usano i pannelli per suddividere un modulo dalla funzione. Ad esempio, potrebbe essere un modulo d'ordine che specifica le opzioni di mailing diretto, ad esempio quali immediato del vettore da usare. Tutte le opzioni in un riquadro di raggruppamento consente all'utente di un segnale visivo logico. In fase di progettazione tutti i controlli possono essere spostati facilmente, ovvero quando si sposta il <xref:System.Windows.Forms.Panel> controllare, tutti i controlli muovendo troppo. I controlli raggruppati in un pannello è possibile accedere tramite relativo <xref:System.Windows.Forms.Control.Controls%2A> proprietà. Questa proprietà restituisce una raccolta di <xref:System.Windows.Forms.Control> istanze, in modo che in genere è necessario eseguire il cast di un controllo recuperate in questo modo al relativo tipo.  
  
## <a name="panel-versus-groupbox"></a>Pannello rispetto a GroupBox  
 Il <xref:System.Windows.Forms.Panel> controllo è simile al <xref:System.Windows.Forms.GroupBox> controllare; tuttavia, solo il <xref:System.Windows.Forms.Panel> controllo può avere le barre di scorrimento e solo il <xref:System.Windows.Forms.GroupBox> controllo Visualizza una didascalia.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Per visualizzare le barre di scorrimento, impostare il <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> proprietà `true`. È anche possibile personalizzare l'aspetto del pannello, impostando il <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, e <xref:System.Windows.Forms.Panel.BorderStyle%2A> proprietà. Per altre informazioni sul <xref:System.Windows.Forms.Control.BackColor%2A> e <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà, vedere [come: Impostare lo sfondo di un controllo Panel](how-to-set-the-background-of-a-windows-forms-panel.md). Il <xref:System.Windows.Forms.Panel.BorderStyle%2A> proprietà determina se il pannello è delineato da alcun bordo visibile (<xref:System.Windows.Forms.BorderStyle.None>), una linea semplice (<xref:System.Windows.Forms.BorderStyle.FixedSingle>), o una riga nascosta (<xref:System.Windows.Forms.BorderStyle.Fixed3D>).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Panel>
- [Controllo GroupBox](groupbox-control-windows-forms.md)
- [Procedura: Controlli di gruppo con il controllo Panel di Windows Form usando la finestra di progettazione](group-controls-with-wf-panel-control-using-the-designer.md)
- [Procedura: Impostare lo sfondo di un controllo Panel Windows Form usando la finestra di progettazione](how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
