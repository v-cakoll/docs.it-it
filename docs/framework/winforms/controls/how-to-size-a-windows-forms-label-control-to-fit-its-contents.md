---
title: Ridimensionare un controllo Label per adattarne il contenuto
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 6a563693feaa5074f5d13f0b82cc4d0305a79c23
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743779"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>Procedura: ridimensionare un controllo Label Windows Form in base al contenuto
Il Windows Forms controllo <xref:System.Windows.Forms.Label> può essere a riga singola o a più righe e può essere a dimensione fissa oppure può ridimensionarsi automaticamente per adattarlo alla didascalia. Il <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà consente di ridimensionare i controlli per adattarli a didascalie più grandi o più piccole, operazione particolarmente utile se la didascalia cambierà in fase di esecuzione.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>Per ridimensionare dinamicamente il controllo etichetta per adattarlo al contenuto  
  
1. Impostarne la proprietà <xref:System.Windows.Forms.Label.AutoSize%2A> su `true`.  
  
 Se <xref:System.Windows.Forms.Label.AutoSize%2A> è impostato su `false`, le parole specificate nella proprietà <xref:System.Windows.Forms.Label.Text%2A> verrà eseguito il wrapping alla riga successiva, se possibile, ma il controllo non aumenterà.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare tasti di scelta con i controlli Label di Windows Form](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [Panoramica sul controllo Label](label-control-overview-windows-forms.md)
- [Controllo Label](label-control-windows-forms.md)
