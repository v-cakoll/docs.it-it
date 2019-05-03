---
title: 'Procedura: Ridimensionare un controllo Label di Windows Forms in base al contenuto'
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 110aab0c0826bb4b06e22158afd6af37b5406be4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971197"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>Procedura: Ridimensionare un controllo Label di Windows Forms in base al contenuto
I moduli di Windows <xref:System.Windows.Forms.Label> controllo può essere a riga singola o multilinea e dimensioni fisse o può ridimensionare automaticamente in base alla lunghezza della didascalia. Il <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà consente di ridimensionare i controlli per adattarli didascalie ingrandire o ridurre, che risulta particolarmente utile se la didascalia verrà modificato in fase di esecuzione.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>Per rendere un controllo etichetta ridimensioni dinamicamente per adattarsi al contenuto  
  
1. Impostare relativi <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà `true`.  
  
 Se <xref:System.Windows.Forms.Label.AutoSize%2A> è impostata su `false`, le parole specificate nel <xref:System.Windows.Forms.Label.Text%2A> proprietà andrà a capo nella riga successiva, se possibile, ma il controllo non aumenterà.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare le chiavi di accesso con i controlli Label di Windows Form](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [Panoramica sul controllo Label](label-control-overview-windows-forms.md)
- [Controllo Label](label-control-windows-forms.md)
