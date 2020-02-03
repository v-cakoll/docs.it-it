---
title: Cenni preliminari sul controllo Panel
ms.date: 03/30/2017
f1_keywords:
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
ms.openlocfilehash: 3ea86e898e8a3e1ca90ba8e0a6240414702a1a73
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744312"
---
# <a name="panel-control-overview-windows-forms"></a>Cenni preliminari sul controllo Panel (Windows Form)
Windows Forms controlli <xref:System.Windows.Forms.Panel> vengono utilizzati per fornire un raggruppamento identificabile per gli altri controlli. In genere, si utilizzano i pannelli per suddividere un form per funzione. Ad esempio, è possibile avere un modulo di ordine che specifica le opzioni di mailing, ad esempio il gestore della notte da usare. Il raggruppamento di tutte le opzioni in un pannello offre all'utente un segnale visivo logico. In fase di progettazione tutti i controlli possono essere spostati facilmente: quando si sposta il controllo <xref:System.Windows.Forms.Panel>, vengono spostati anche tutti i controlli contenuti. È possibile accedere ai controlli raggruppati in un pannello tramite la relativa proprietà <xref:System.Windows.Forms.Control.Controls%2A>. Questa proprietà restituisce una raccolta di istanze di <xref:System.Windows.Forms.Control>, quindi è in genere necessario eseguire il cast di un controllo recuperato in questo modo al tipo specifico.  
  
## <a name="panel-versus-groupbox"></a>Pannello rispetto a GroupBox  
 Il controllo <xref:System.Windows.Forms.Panel> è simile al controllo <xref:System.Windows.Forms.GroupBox>. Tuttavia, solo il controllo <xref:System.Windows.Forms.Panel> può avere barre di scorrimento e solo il controllo <xref:System.Windows.Forms.GroupBox> Visualizza una didascalia.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Per visualizzare le barre di scorrimento, impostare la proprietà <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> su `true`. È anche possibile personalizzare l'aspetto del pannello impostando le proprietà <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>e <xref:System.Windows.Forms.Panel.BorderStyle%2A>. Per altre informazioni sulle proprietà <xref:System.Windows.Forms.Control.BackColor%2A> e <xref:System.Windows.Forms.Control.BackgroundImage%2A>, vedere [procedura: impostare lo sfondo di un pannello](how-to-set-the-background-of-a-windows-forms-panel.md). La proprietà <xref:System.Windows.Forms.Panel.BorderStyle%2A> determina se il pannello è delineato senza bordo visibile (<xref:System.Windows.Forms.BorderStyle.None>), una linea semplice (<xref:System.Windows.Forms.BorderStyle.FixedSingle>) o una linea ombreggiata (<xref:System.Windows.Forms.BorderStyle.Fixed3D>).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Panel>
- [Controllo GroupBox](groupbox-control-windows-forms.md)
- [Procedura: Raggruppare i controlli con il controllo Panel di Windows Form nella finestra di progettazione](group-controls-with-wf-panel-control-using-the-designer.md)
- [Procedura: Impostare lo sfondo di un controllo Panel di Windows Form con la finestra di progettazione](how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
