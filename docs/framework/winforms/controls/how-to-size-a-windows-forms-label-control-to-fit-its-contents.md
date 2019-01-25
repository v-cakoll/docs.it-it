---
title: 'Procedura: Ridimensionare un controllo Label di Windows Form in base al contenuto'
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 74947e529a472c9e9a681fcb436ce8aff990c0af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640407"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>Procedura: Ridimensionare un controllo Label di Windows Form in base al contenuto
I moduli di Windows <xref:System.Windows.Forms.Label> controllo può essere a riga singola o multilinea e dimensioni fisse o può ridimensionare automaticamente in base alla lunghezza della didascalia. Il <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà consente di ridimensionare i controlli per adattarli didascalie ingrandire o ridurre, che risulta particolarmente utile se la didascalia verrà modificato in fase di esecuzione.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>Per rendere un controllo etichetta ridimensioni dinamicamente per adattarsi al contenuto  
  
1.  Impostare relativi <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà `true`.  
  
 Se <xref:System.Windows.Forms.Label.AutoSize%2A> è impostata su `false`, le parole specificate nel <xref:System.Windows.Forms.Label.Text%2A> proprietà andrà a capo nella riga successiva, se possibile, ma il controllo non aumenterà.  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Creare le chiavi di accesso con i controlli Label di Windows Form](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)
- [Panoramica sul controllo Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)
- [Controllo Label](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
