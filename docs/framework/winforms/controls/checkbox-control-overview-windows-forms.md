---
title: Cenni preliminari sul controllo CheckBox (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
ms.openlocfilehash: 003e57db16c35b519d3948fc24e82a94a5c3744d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713449"
---
# <a name="checkbox-control-overview-windows-forms"></a>Cenni preliminari sul controllo CheckBox (Windows Form)
Il controllo di Windows Form <xref:System.Windows.Forms.CheckBox> indica se una determinata condizione è attiva o disattivata. Viene usato comunemente per presentare all'utente la selezione di valori Sì/No o True/False. È possibile usare i controlli della casella di controllo in gruppi, per visualizzare e consentire all'utente la selezione di una o più opzioni.  
  
 Il controllo casella di controllo è simile al controllo pulsante di opzione in quanto ognuna viene utilizzata per indicare una selezione effettuata dall'utente. Si differenziano in quanto selezionabile solo un pulsante di opzione in un gruppo alla volta. Con il controllo casella di controllo, tuttavia, è possibile selezionare un numero qualsiasi delle caselle di controllo.  
  
 Una casella di controllo possono essere collegata agli elementi in un database tramite data binding semplice. Inoltre è possibile raggruppare diverse caselle di controllo utilizzando il <xref:System.Windows.Forms.GroupBox> controllo. Ciò è utile per aspetto visivo, nonché per la progettazione dell'interfaccia utente, poiché i controlli raggruppati possono essere spostati tra loro in Progettazione Windows form. Per altre informazioni, vedere [Windows Forms Data Binding](../windows-forms-data-binding.md) e [controllo GroupBox](groupbox-control-windows-forms.md).  
  
 Il <xref:System.Windows.Forms.CheckBox> controllo ha due proprietà importanti <xref:System.Windows.Forms.CheckBox.Checked%2A> e <xref:System.Windows.Forms.CheckBox.CheckState%2A>. Il <xref:System.Windows.Forms.CheckBox.Checked%2A> proprietà restituisce `true` o `false`. Il <xref:System.Windows.Forms.CheckBox.CheckState%2A> proprietà restituisce <xref:System.Windows.Forms.CheckState.Checked> o <xref:System.Windows.Forms.CheckState.Unchecked>; oppure, se il <xref:System.Windows.Forms.CheckBox.ThreeState%2A> viene impostata su `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> potrebbero restituire anche <xref:System.Windows.Forms.CheckState.Indeterminate>. Nello stato indeterminato, viene visualizzata con un aspetto in grigio per indicare che l'opzione è disponibile.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.CheckBox>
- [Procedura: Impostare le opzioni con i controlli CheckBox di Windows Form](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [Procedura: Rispondere a un Windows Form controlli CheckBox](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [Controllo CheckBox](checkbox-control-windows-forms.md)
