---
title: 'Procedura: ridimensionare un controllo Label Windows Form in base al contenuto'
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: e067966b606d77ceb9d11d2784c0d5f73ad332a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>Procedura: ridimensionare un controllo Label Windows Form in base al contenuto
Windows Form <xref:System.Windows.Forms.Label> controllo può essere a riga singola o multilinea e dimensioni fisse o automaticamente ridimensionato in base alla lunghezza della didascalia. Il <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà consente di ridimensionare i controlli per adattarli didascalie maggiore o minore, particolarmente utile se la didascalia verrà modificato in fase di esecuzione.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>Per rendere un controllo etichetta ridimensioni dinamicamente per adattarsi al contenuto  
  
1.  Impostare il relativo <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà `true`.  
  
 Se <xref:System.Windows.Forms.Label.AutoSize%2A> è impostato su `false`, le parole specificate nel <xref:System.Windows.Forms.Label.Text%2A> proprietà eseguirà il wrapping alla riga successiva, se possibile, ma il controllo non aumenterà.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Creare tasti di scelta con i controlli Label di Windows Form](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)  
 [Panoramica sul controllo Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [Controllo Label](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
