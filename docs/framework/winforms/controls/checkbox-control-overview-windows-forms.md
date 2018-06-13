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
ms.openlocfilehash: 54a0bba3923626398fb4d1b0af753177dfaa09a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524144"
---
# <a name="checkbox-control-overview-windows-forms"></a>Cenni preliminari sul controllo CheckBox (Windows Form)
Il controllo di Windows Form <xref:System.Windows.Forms.CheckBox> indica se una determinata condizione è attiva o disattivata. Viene usato comunemente per presentare all'utente la selezione di valori Sì/No o True/False. È possibile usare i controlli della casella di controllo in gruppi, per visualizzare e consentire all'utente la selezione di una o più opzioni.  
  
 Il controllo casella di controllo è simile al controllo pulsante di opzione in quanto ognuna viene utilizzata per indicare una selezione effettuata dall'utente. Si differenziano in cui è possibile selezionare solo un pulsante di opzione in un gruppo alla volta. Con il controllo casella di controllo, tuttavia, è possibile selezionare un numero qualsiasi di caselle di controllo.  
  
 Una casella di controllo possono essere collegata a elementi in un database utilizzando l'associazione dati. Inoltre è possibile raggruppare più caselle di controllo utilizzando il <xref:System.Windows.Forms.GroupBox> controllo. Ciò è utile per l'aspetto visivo, nonché per la progettazione dell'interfaccia utente, poiché i controlli raggruppati possono essere spostati insieme nella finestra di progettazione form. Per ulteriori informazioni, vedere [Windows Forms Data Binding](../../../../docs/framework/winforms/windows-forms-data-binding.md) e [controllo GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).  
  
 Il <xref:System.Windows.Forms.CheckBox> controllo ha due proprietà importanti, <xref:System.Windows.Forms.CheckBox.Checked%2A> e <xref:System.Windows.Forms.CheckBox.CheckState%2A>. Il <xref:System.Windows.Forms.CheckBox.Checked%2A> restituisce proprietà `true` o `false`. Il <xref:System.Windows.Forms.CheckBox.CheckState%2A> restituisce proprietà <xref:System.Windows.Forms.CheckState.Checked> o <xref:System.Windows.Forms.CheckState.Unchecked>; oppure, se il <xref:System.Windows.Forms.CheckBox.ThreeState%2A> è impostata su `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> potrebbero restituire anche <xref:System.Windows.Forms.CheckState.Indeterminate>. In stato indeterminato, viene visualizzata come inattiva per indicare che l'opzione è disponibile.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.CheckBox>  
 [Procedura: Impostare opzioni con i controlli CheckBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [Procedura: Rispondere alla selezione di controlli CheckBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [Controllo CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
